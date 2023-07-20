<script setup>
import axios from "axios";
import { ref } from "vue";
import { toast } from "vue3-toastify";
import "vue3-toastify/dist/index.css";

const text = ref("");
const phone = ref("");
const lesson = ref("");

const handleForm = () => {
  axios.post(
    "https://api.telegram.org/bot6350411149:AAFouN9lI1qD5AhHEGKfhamHHm_3EzmzQ2A/sendMessage",
    {
      chat_id: -1001989077847,
      text: `<b>Ismi:</b> ${text.value}\n<b>Telofon Raqami:</b> ${phone.value}\n<b>Tanlagan Fani:</b> ${lesson.value}`,
      parse_mode: "HTML",
    }
  );

  text.value = undefined;
  phone.value = undefined;
  lesson.value = undefined;

  toast.success("Xabaringiz yuborildi tez orada siz bilan bo'g'lanishadi.", {
    autoClose: 5000,
  });
};
</script>

<template>
  <div
    class="w-full mx-auto max-w-7xl px-5 sm:px-8 md:px-14 lg:px-5"
    id="login"
  >
    <div class="mt-10 w-full flex mx-auto lg:mx-0">
      <div class="flex sm:flex-row flex-col gap-5 w-full">
        <form
          @submit.prevent="handleForm"
          class="py-1 pl-6 w-full flex-col pr-6 flex gap-3 items-center text-heading-3 shadow-lg shadow-box-shadow border border-box-border bg-box-bg rounded-lg ease-linear focus-within:bg-body focus-within:border-primary"
        >
          <h1
            class="mt-5 text-2xl/tight text-center sm:text-4xl/tight md:text-4xl/tight xl:text-5xl/tight font-bold text-heading-1"
          >
            O’zbekistondagi Sifatli Ta’lim markazi!
          </h1>
          <p class="md:text-lg text-heading-3 text-center">
            O'quv markazimizga siz ham qo’shiling va biz bilan yuqori
            natijalarga erishing!
          </p>
          <div class="flex sm:flex-row flex-col gap-6 mt-3">
            <div class="flex items-center sm:flex-row gap-4 w-full">
              <div
                class="py-1 pl-6 w-full pr-1 flex gap-3 items-center text-heading-3 shadow-lg shadow-box-shadow border border-box-border bg-box-bg rounded-full ease-linear focus-within:bg-body focus-within:border-primary"
              >
                <span class="min-w-max pr-2 border-r border-box-border">
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="20"
                    fill="none"
                    viewBox="0 0 16 16"
                    stroke-width="1.5"
                    stroke="currentColor"
                    class="w-5 h-5 opacity-100 dark:text-white text-black"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      d="M8 8a3 3 0 1 0 0-6 3 3 0 0 0 0 6zm2-3a2 2 0 1 1-4 0 2 2 0 0 1 4 0zm4 8c0 1-1 1-1 1H3s-1 0-1-1 1-4 6-4 6 3 6 4zm-1-.004c-.001-.246-.154-.986-.832-1.664C11.516 10.68 10.289 10 8 10c-2.29 0-3.516.68-4.168 1.332-.678.678-.83 1.418-.832 1.664h10z"
                    ></path>
                  </svg>
                </span>

                <input
                  type="text"
                  id="text"
                  v-model="text"
                  required
                  placeholder="Ismingiz"
                  class="w-full py-3 outline-none bg-transparent rounded-full"
                />
              </div>
            </div>

            <div class="flex items-center sm:flex-row gap-4 w-full">
              <div
                class="py-1 pl-6 w-full pr-1 flex gap-3 items-center text-heading-3 shadow-lg shadow-box-shadow border border-box-border bg-box-bg rounded-full ease-linear focus-within:bg-body focus-within:border-primary"
              >
                <span class="min-w-max pr-2 border-r border-box-border">
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="20"
                    fill="none"
                    viewBox="0 0 16 16"
                    stroke-width="1.5"
                    stroke="currentColor"
                    class="w-5 h-5 opacity-100 dark:text-white text-black"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      d="M3.654 1.328a.678.678 0 0 0-1.015-.063L1.605 2.3c-.483.484-.661 1.169-.45 1.77a17.568 17.568 0 0 0 4.168 6.608 17.569 17.569 0 0 0 6.608 4.168c.601.211 1.286.033 1.77-.45l1.034-1.034a.678.678 0 0 0-.063-1.015l-2.307-1.794a.678.678 0 0 0-.58-.122l-2.19.547a1.745 1.745 0 0 1-1.657-.459L5.482 8.062a1.745 1.745 0 0 1-.46-1.657l.548-2.19a.678.678 0 0 0-.122-.58L3.654 1.328zM1.884.511a1.745 1.745 0 0 1 2.612.163L6.29 2.98c.329.423.445.974.315 1.494l-.547 2.19a.678.678 0 0 0 .178.643l2.457 2.457a.678.678 0 0 0 .644.178l2.189-.547a1.745 1.745 0 0 1 1.494.315l2.306 1.794c.829.645.905 1.87.163 2.611l-1.034 1.034c-.74.74-1.846 1.065-2.877.702a18.634 18.634 0 0 1-7.01-4.42 18.634 18.634 0 0 1-4.42-7.009c-.362-1.03-.037-2.137.703-2.877L1.885.511z"
                    ></path>
                  </svg>
                </span>

                <input
                  type="phone"
                  name="phone"
                  required
                  v-model="phone"
                  id="phone"
                  placeholder="Telefon raqamingiz"
                  class="w-full py-3 outline-none bg-transparent rounded-full"
                />
              </div>
            </div>

            <div class="flex items-center sm:flex-row gap-4 w-full">
              <div
                class="py-1 pl-6 w-full pr-1 flex gap-3 items-center text-heading-3 shadow-lg shadow-box-shadow border border-box-border bg-box-bg rounded-full ease-linear focus-within:bg-body focus-within:border-primary"
              >
                <span class="min-w-max pr-2 border-r border-box-border">
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="20"
                    fill="none"
                    viewBox="0 0 16 16"
                    stroke-width="1.5"
                    stroke="currentColor"
                    class="w-5 h-5 opacity-100 dark:text-white text-black"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      d="M1 2.828c.885-.37 2.154-.769 3.388-.893 1.33-.134 2.458.063 3.112.752v9.746c-.935-.53-2.12-.603-3.213-.493-1.18.12-2.37.461-3.287.811V2.828zm7.5-.141c.654-.689 1.782-.886 3.112-.752 1.234.124 2.503.523 3.388.893v9.923c-.918-.35-2.107-.692-3.287-.81-1.094-.111-2.278-.039-3.213.492V2.687zM8 1.783C7.015.936 5.587.81 4.287.94c-1.514.153-3.042.672-3.994 1.105A.5.5 0 0 0 0 2.5v11a.5.5 0 0 0 .707.455c.882-.4 2.303-.881 3.68-1.02 1.409-.142 2.59.087 3.223.877a.5.5 0 0 0 .78 0c.633-.79 1.814-1.019 3.222-.877 1.378.139 2.8.62 3.681 1.02A.5.5 0 0 0 16 13.5v-11a.5.5 0 0 0-.293-.455c-.952-.433-2.48-.952-3.994-1.105C10.413.809 8.985.936 8 1.783z"
                    ></path>
                  </svg>
                </span>

                <input
                  enabled
                  type="lesson"
                  name="lesson"
                  required
                  v-model="lesson"
                  id="lesson"
                  placeholder="Qiziqqan faningiz"
                  class="w-full py-3 outline-none bg-transparent rounded-full"
                />
              </div>
            </div>
          </div>
          <button
            type="submit"
            class="px-6 py-3 mt-5 mb-5 w-[60%] sm:w-[35%] md:w-[25%] flex justify-center rounded-full bg-[#1d4ed8] outline-none overflow-hidden border duration-300 ease-linear after:absolute after:inset-x-0 after:aspect-square after:scale-0 after:opacity-70 after:origin-center after:duration-300 after:ease-linear after:rounded-full after:top-0 after:left-0 hover:after:opacity-100 hover:after:scale-[2.5] border-transparent relative after:bg-orange-500 hover:border-orange-500"
          >
            <span class="flex relative z-[5] text-white"> Yuborish </span>
            <!-- <span class="flex sm:hidden relative z-[5]">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                stroke="currentColor"
                class="w-5 h-5"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M6 12L3.269 3.126A59.768 59.768 0 0121.485 12 59.77 59.77 0 013.27 20.876L5.999 12zm0 0h7.5"
                ></path>
              </svg>
            </span> -->
          </button>
        </form>
      </div>
    </div>
  </div>
</template>

<style scoped>
input:focus {
  background-color: none !important;
  -webkit-appearance: none;
}
</style>
