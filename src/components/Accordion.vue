<template>
  <div
    class="accordion bg-box-bg mt-10 rounded-lg border-box-border border p-4"
  >
    <div
      v-for="(item, index) in items"
      :key="index"
      class="accordion-item my-4"
      :class="{ active: item.active }"
    >
      <div
        class="accordion-header dark:text-white text-black text-heading-1 font-semibold text-sm md:text-2xl cursor-pointer border border-box-border rounded-lg pl-5 py-2 sm:pr-5 pr-2"
        @click="toggleItem(index)"
      >
        <div class="flex justify-between w-full items-center">
          {{ item.header }}

          <svg
            v-if="!item.active"
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-6 h-6"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M19.5 8.25l-7.5 7.5-7.5-7.5"
            />
          </svg>
          <svg
            v-if="item.active"
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-6 h-6"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M4.5 15.75l7.5-7.5 7.5 7.5"
            />
          </svg>
        </div>

        <div class="accordion-content text-base pl-0 p-4" v-if="item.active">
          {{ item.content }}
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const items = ref([
  {
    header: "O’quv markazingizda qanday sharoitlar bor ?",
    content: "Content for Item 1",
    active: false,
  },
  {
    header: "Darslar qanday metodlar yordamida o'tiladi ?",
    content: "Content for Item 2",
    active: false,
  },
  {
    header: "O'qiv markazilar qanday yutuqlarga erishgan ?",
    content: "Content for Item 3",
    active: false,
  },
  {
    header: "O’quv markazingizda qanday sharoitlar bor ?",
    content: "Content for Item 1",
    active: false,
  },
  {
    header: "Darslar qanday metodlar yordamida o'tiladi ?",
    content: "Content for Item 2",
    active: false,
  },
  {
    header: "O'qiv markazilar qanday yutuqlarga erishgan ?",
    content: "Content for Item 3",
    active: false,
  },
]);

const toggleItem = (index) => {
  items.value.forEach((item, i) => {
    item.active = i === index ? !item.active : false;
  });
};
</script>

<style>
/* Add your accordion styles here */
</style>
