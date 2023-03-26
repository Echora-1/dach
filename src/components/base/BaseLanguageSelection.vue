<template>
  <div class="wrapper">
    <label :for="id" class="base-label">
      {{ label }}
    </label>
    <div
      :class="[
        'base-input-wrapper',
        { 'base-input-wrapper_focused': focused || isDropdownOpen },
      ]"
    >
      <input
        :id="id"
        v-model="searchValue"
        class="base-input"
        v-bind="$attrs"
        :placeholder="$attrs.placeholder"
        readonly
        @focus="focusHandler"
        @input="inputHandler"
        @blur="blurHandler"
      />
    </div>
    <div v-show="isDropdownOpen" class="list-selector___dropdown">
      <ul>
        <li
          v-for="item in unselectedItems"
          :key="item.id"
          @click="onItemClick(item)"
        >
          {{ item[itemKey] }}
        </li>
        <li v-show="!filteredList.length" class="empty">Ничего не найдено</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    value: {
      type: String,
      default: "",
    },

    id: {
      type: String,
      default: "",
    },

    label: {
      type: String,
      default: "",
    },

    list: {
      type: Array,
    },

    itemKey: {
      type: String,
    },

    defaultValue: {
      type: Object,
    },
  },

  data() {
    return {
      focused: false,
      isDropdownOpen: false,
      selectedListItem: {},
      filteredList: this.list,
      searchValue: "",
    };
  },

  computed: {
    unselectedItems() {
      return this.list.filter((item) => item.id !== this.selectedListItem.id);
    },
  },

  watch: {
    selectedListItem() {
      this.$emit("selected", this.selectedListItem);
    },
  },

  created() {
    if (this.defaultValue) {
      this.searchValue = this.defaultValue[this.itemKey];
      this.selectedListItem = this.defaultValue;
    }
  },

  methods: {
    inputHandler() {
      this.isDropdownOpen = true;
    },

    focusHandler() {
      this.focused = true;
      this.isDropdownOpen = true;
    },

    blurHandler() {
      this.focused = false;
    },

    hideDropdown() {
      this.isDropdownOpen = false;
    },

    onItemClick(item) {
      this.selectedListItem = item;
      this.searchValue = item[this.itemKey];
      this.isDropdownOpen = false;
    },

    getSearchItem() {
      this.filteredList = this.list.filter((item) =>
        item[this.itemKey]
          .toLowerCase()
          .includes(this.searchValue.toLowerCase())
      );
    },
  },
};
</script>

<style scoped lang="scss">
.wrapper {
  position: relative;
}

.base-input-wrapper {
  background: transparent;
  border: 1px solid transparent;
  border-radius: 20px;
  width: 100%;
  &:hover {
  }
}

.base-input {
  width: 48px;
  height: 32px;
  margin: 0;
  border: none;
  outline: none;
  padding: 2px 17px 2px 4px;
  background-color: transparent;
  background-repeat: no-repeat;
  background-position: center right;
  background-image: url("@/assets/images/vector.svg");
  font-weight: 600;
  font-size: 18px;
  line-height: 30px;
  cursor: pointer;
}

.base-label {
  display: none;
}

.list-selector___dropdown {
  max-height: 100px;
  width: 100%;
  position: absolute;
  z-index: 2;
  overflow-y: auto;
  ul {
    list-style: none;
    margin: 0;
    padding: 0;
    font-size: 16px;
    line-height: 24px;
  }
  li {
    font-weight: 600;
    font-size: 18px;
    line-height: 30px;
    padding: 5px 17px 5px 5px;
    cursor: pointer;
  }
}
.empty {
  text-align: center;
  font-size: 12px;
}

li.empty:hover {
  background-color: transparent;
}
</style>
