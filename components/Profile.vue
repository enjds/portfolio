<template>
  <section class="flex flex-col max-w-md bg-white p-5 rounded-xl shadow-lg">
    <div class="flex-shrink-0 rounded-xl overflow-hidden bg-gray-200 mb-5">
        <img class="h-80 w-full object-cover" v-bind:src="bio.photo" />
    </div>
    
    <div>
      <div class="flex flex-col">
        <div>
          <h2>{{ bio.name }}</h2>
          <div class="flex flex-row mb-2">
             <div v-on:click="openLink(bio.linkedin)" class="flex-shrink-0 h-5 w-5 overflow-hidden bg-gray-200 cursor-pointer mr-2">
                <img class="h-full w-full object-cover" src="/logos/linkedin.jpeg" />
              </div>
              <div v-on:click="openLink(bio.upwork)" class="flex-shrink-0 h-5 w-5 overflow-hidden bg-gray-200 cursor-pointer mr-2">
                <img class="h-full w-full object-cover" src="/logos/upwork.jpeg" />
              </div>
          </div>
         
          <p class="text-gray-400">{{ bio.title }}</p>
        </div>
        <div class="text-justify my-8">
            <p class="flex flex-row items-center">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 inline-block mr-4" viewBox="0 0 20 20" fill="currentColor">
                    <path d="M2.003 5.884L10 9.882l7.997-3.998A2 2 0 0016 4H4a2 2 0 00-1.997 1.884z" />
                    <path d="M18 8.118l-8 4-8-4V14a2 2 0 002 2h12a2 2 0 002-2V8.118z" />
                </svg>
                <a v-bind:href="'mailto:' + bio.email" class="font-medium text-lg flex-wrap">{{ bio.email }}</a>
            </p>
            <p class="flex flex-row items-center">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 inline-block mr-4" viewBox="0 0 20 20" fill="currentColor">
                    <path d="M2 3a1 1 0 011-1h2.153a1 1 0 01.986.836l.74 4.435a1 1 0 01-.54 1.06l-1.548.773a11.037 11.037 0 006.105 6.105l.774-1.548a1 1 0 011.059-.54l4.435.74a1 1 0 01.836.986V17a1 1 0 01-1 1h-2C7.82 18 2 12.18 2 5V3z" />
                </svg>
                <a v-bind:href="'tel:' + bio.mobile" class="font-medium text-lg">{{ bio.mobile }}</a>
            </p>
            
        </div>
      </div>
      <p class="text-gray-400" v-html="bio.description"></p>
    </div>
  </section>
</template>

<style scoped>
  p {
      font-size: 18px;
      line-height: 21.94px;
  }
</style>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
    data() {
      return {
        bio: {
          name: "Benjo D.",
          title: "Professional Web and Mobile Developer",
          email: "benjo.freelancer@gmail.com",
          linkedin: 'https://www.linkedin.com/in/enjds',
          upwork: 'https://www.upwork.com/o/profiles/users/~017d71f56bf08ff493/',
          mobile: "(+639) 457 915 603",
          photo: "/images/me.jpeg",
          description: `
              I specialize in hybrid mobile app development and responsive web apps. I have a number of projects listed that you can take a look.<br><br>
              With my 5+ years of work experience, you can be confident that I will complete your project to your absolute satisfaction and ON-TIME. If you are interested in working with me I am available to contact 24/7.
          `,
        },
      };
    },
    methods: {
       openLink: function (link: string) {
           window.open(link)
       }
    }
});
</script>