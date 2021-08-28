<template>
  <section class="flex flex-col max-w-md bg-white p-5 rounded-xl shadow-lg">
    <h2 class="font-medium mb-11">Hobbies</h2>
    <div
      v-for="(hobby, index) in hobbies"
      v-bind:key="index"
      class="flex flex-col mb-9">
      <div class="h-32 w-full bg-gray-200 mr-4 rounded-xl overflow-hidden">
        <img class="h-full w-full object-cover" v-bind:src="hobby.imageUrl" />
      </div>
      <div class="flex-1">
        <h3 class="mt-6 mb-2">{{ hobby.name }}</h3>
        <p class="text-gray-400">{{ hobby.description }}</p>
      </div>
    </div>
  </section>
</template>

<style scoped>
    h3 {
        font-size: 18px;
        font-weight: 600;
        line-height: 21.94px;
    }
  p {
      font-size: 16px;
      line-height: 19.5px;
  }
</style>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
    data() {
        return {
            hobbies: [
                {
                    imageUrl: '/images/gaming.jpeg',
                    name: 'Gaming',
                    description: 'Playing Mobile Legends or solving word puzzles',
                },
                {
                    imageUrl: '/images/cooking.jpeg',
                    name: 'Cooking',
                    description: 'Loves to cook sinigang',
                },
                {
                    imageUrl: '/images/fishing.jpeg',
                    name: 'Fishing',
                    description: 'The thrill of waiting and the art of being patient',
                },
            ]
        }
    }
});
</script>