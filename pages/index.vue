<template>
  <main class="bg-gray-200 h-full w-full py-10">
    <section class="max-w-screen-xl flex mx-auto">
      <div>
        <Profile />
        <Experiences class="my-11" />
        <Hobbies />
      </div>

      <div class="w-full ml-8">
        <Projects />
      </div>
    </section>
  </main>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({});
</script>
