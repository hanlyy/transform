<!-- Кнопки в шапке и подвале -->

<script setup>
import { useTransformStore } from "./../../store/TransformStore";
const transformStore = useTransformStore();

import { useRouter } from "vue-router";
const router = useRouter();

const props = defineProps({
  textColor: String,
  targetPage: String,
});

function changePage() {
  router.push({ name: props.targetPage });
  //Возврат наверх страницы
  window.scrollTo({
    top: 0,
    left: 0,
    behavior: "smooth",
  });
}
</script>

<template>
  <button
    @click="changePage"
    class="uppercase font-medium text-base font-main"
    :style="{
      textDecoration: $route.name === props.targetPage ? 'underline' : 'none',
    }"
  >
    <slot></slot>
  </button>
</template>
