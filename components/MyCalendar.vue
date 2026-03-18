<script setup>
import { ref } from "vue";

const date = ref({ start: undefined, end: undefined });

const formatDate = (d) => {
  if (!d) return "";
  // Handle CalendarDate from @internationalized/date used by Nuxt UI Calendar
  if (d.year && d.month && d.day) {
    const jsDate = new Date(d.year, d.month - 1, d.day);
    return new Intl.DateTimeFormat("en-GB", {
      day: "2-digit",
      month: "short",
      year: "numeric",
    }).format(jsDate);
  }
  return "";
};
</script>

<template>
  <div class="flex flex-col items-center justify-center w-full gap-4">
    <div class="flex gap-4 font-medium text-lg min-h-[28px]">
      <div v-if="date.start" class="text-primary">
        {{ formatDate(date.start) }}
      </div>
      <div v-else class="text-gray-400">Start Date</div>
      <span class="text-gray-500">-</span>
      <div v-if="date.end" class="text-primary">{{ formatDate(date.end) }}</div>
      <div v-else class="text-gray-400">End Date</div>
    </div>
    <UCalendar
      v-model="date"
      class="w-auto h-auto"
      range
      :number-of-months="3"
    />
  </div>
</template>
