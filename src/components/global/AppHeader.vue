<script setup>
import { useTransformStore } from "../../store/TransformStore";
const transformStore = useTransformStore();
</script>

<template>
  <header
    class="w-full h-24 bg-white flex flex-row justify-between items-center px-20"
  >
    <div class="grid grid-rows-1 grid-cols-3 gap-16">
      <NavBtn :targetPage="`about`">о нас</NavBtn>
      <NavBtn :targetPage="`tariffs`">Программы</NavBtn>
      <NavBtn :targetPage="`results`">Результаты</NavBtn>
    </div>

    <button
      @click="$router.push({ name: 'main' })"
      class="font-main uppercase text-2xl font-bold cursor-pointer"
    >
      Трансформация
    </button>

    <div>
      <NavBtn :targetPage="`contacts`" class="mr-16">Контакты</NavBtn>
      <FeedBackBtn />
    </div>
  </header>
</template>
