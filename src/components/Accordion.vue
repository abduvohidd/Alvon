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
    header: "O’quv markazingizda qanday sharoitlar bor ? ",
    content:
      "Yorug' va keng xonalar, xonada zamonaviy proyektor va qular joylashuv bularning barchasi bizning Zakiy Academy o'quv markazimizda...",
    active: false,
  },
  {
    header: "Darslar qanday metodlar yordamida o'tiladi ?",
    content: `“Kichik guruhlarda ishlash” metodi. Bu metodda ta’lim beruvchi tomonidan aniq ko‘rsatmalar beriladi kichik guruhlar esa topshiriqni bajarishga kirishadilar. Natijasi - muloqotga kirishish ko‘nikmasining takomillashishiga olib keladi.
              “Davra suhbati” metodi, bu metod berilgan muammo yoki savollar yuzasidan ta’lim oluvchilar tomonidan o‘z fikr - mulohazalarini bildirish orqali olib boriladigan o‘qitish metodidir. Natijasi - ta’lim oluvchilar berilgan mavzu bo‘yicha o‘zlarining bilimlarini qisqa va aniq ifoda eta oladilar.
      `,
    active: false,
  },
  {
    header: "O'quv markazimiz qanday yutuqlarga erishgan ?",
    content:
      "Hozirgi yutuqlarimiz: Matematika fanidan 2023-yil OTM (Oliy ta'lim muassasasi) ga kirish imtihonlariga topshirgan 10 ta abituriyentimizdan 9 tasi talabalik baxtiga sazovor bo'lishgan, 90% lik natija.",
    active: false,
  },
  {
    header: "Kursni tanlashdan avval bilim darajasini qanday aniqlash mumkin ?",
    content:
      "Shu maqsadda barcha yangi talabalarimiz uchun test sinovlari o’tkazamiz. Uning natijalariga ko’ra mutaxassislarimiz talabalarni guruhlarga ajratishadi. Avvalgi kurslarni tamomlagan talabamiz keyingi bosqichga o’ta olish yoki olmasligini ham xuddi shu usul orqali aniqlaymiz.",
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
