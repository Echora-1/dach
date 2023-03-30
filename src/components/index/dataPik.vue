<template>
  <div class="datepicker">
    <input type="text" :value="formattedDate" @focus="showCalendar" />
    <div class="calendar" v-if="true">
      <div class="header">
        <button @click="previousMonth">&lt;</button>
        <span>{{ currentMonth }}</span>
        <button @click="nextMonth">&gt;</button>
      </div>
      <div class="days">
        <div
          v-for="day in daysInMonth"
          :key="day"
          :class="{
            today: day === todayDay,
            selected: day === selectedDay,
          }"
          @click="selectDay(day)"
        >
          {{ day }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref, computed } from "vue";

export default {
  setup() {
    const today = new Date();
    const todayDay = today.getDate();
    const selectedDate = ref(today);
    const isCalendarVisible = ref(false);

    function showCalendar() {
      isCalendarVisible.value = true;
    }

    function hideCalendar() {
      isCalendarVisible.value = false;
    }

    function selectDay(day) {
      selectedDate.value.setDate(day);
      hideCalendar();
    }

    function previousMonth() {
      const currentMonth = selectedDate.value.getMonth();
      selectedDate.value.setMonth(currentMonth - 1);
    }

    function nextMonth() {
      const currentMonth = selectedDate.value.getMonth();
      selectedDate.value.setMonth(currentMonth + 1);
    }

    const formattedDate = computed(() => {
      const options = { year: "numeric", month: "short", day: "numeric" };
      return selectedDate.value.toLocaleDateString("en-US", options);
    });

    const currentMonth = computed(() => {
      const options = { month: "long", year: "numeric" };
      return selectedDate.value.toLocaleDateString("en-US", options);
    });

    const daysInMonth = computed(() => {
      const year = selectedDate.value.getFullYear();
      const month = selectedDate.value.getMonth();
      const days = new Date(year, month + 1, 0).getDate();
      return Array.from({ length: days }, (_, i) => i + 1);
    });

    return {
      selectedDate,
      isCalendarVisible,
      formattedDate,
      currentMonth,
      daysInMonth,
      showCalendar,
      hideCalendar,
      selectDay,
      previousMonth,
      nextMonth,
      todayDay,
    };
  },
};
</script>

<style>
.datepicker {
  position: relative;
  display: inline-block;
}

.datepicker input {
  padding: 6px;
  border-radius: 3px;
  border: 1px solid #ccc;
}

.datepicker .calendar {
  position: relative;
  top: 100%;
  left: 0;
  z-index: 1;
  background-color: #fff;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  border-radius: 3px;
  padding: 10px;
}

.datepicker .header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 10px;
}

.datepicker .header button {
  background-color: transparent;
  border: none;
  cursor: pointer;
}

.datepicker .days {
  display: grid;
  grid-template-columns: repeat(7, 1fr);
  gap: 5px;
}

.datepicker .days div {
  padding: 5px;
  text-align: center;
  cursor: pointer;
  border-radius: 3px;
}

.datepicker .days div:hover {
  background-color: #eee;
}

.datepicker .days div.today {
  background-color: #eee;
}

.datepicker .days div.selected {
  background-color: #007aff;
  color: #fff;
}
</style>
