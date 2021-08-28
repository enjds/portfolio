<template>
   <section  class="flex flex-col max-w-md bg-white p-5 rounded-xl shadow-lg">
       <h2 class="font-medium mb-11">Experiences</h2>
       <div v-for="(xp, index) in experiences" v-bind:key="index" class="flex mb-10">
            <div class="h-20 w-20 bg-gray-200 mr-4">
                 <img class="h-20 w-full object-cover" v-bind:src="xp.companyLogo" />
            </div>
            <div class="flex-1">
                <span class="text-gray-400 mb-3">{{ xp.tenure }}</span>
                <h3 class="mb-8">{{ xp.position }}</h3>
                <p class="text-gray-400">{{ xp.role }}</p>
            </div>
       </div>
   </section>
</template>

<style scoped>
  p {
      font-size: 16px;
      line-height: 19.5px;
  }
</style>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
    data() {
        return {
            experiences: [
                {
                    companyLogo: '/images/atrax.png',
                    tenure: 'Feb 2020 - current',
                    position: 'Frontend Project Contractor',
                    role: 'Contractor of mobile and web projects'
                },
                {
                    companyLogo: '/images/upwork.jpeg',
                    tenure: 'Oct 2019 - current',
                    position: 'Professional Mobile and Web Developer',
                    role: 'Full time freelancer. Helping client achieve pixel perfect, responsive and fully optimize app both in mobile and web.'
                },
                {
                    companyLogo: '/images/sunlife.jpeg',
                    tenure: 'May 2017 - Dec 2020',
                    position: 'Mobile Systems Analyst',
                    role: '(SME)Subject Matter Expert in mobile and web app who have led 4 team members. Biggest accomplishment during my time was the automation of app releases for both web and mobile. Handled multiple projects.'
                },
                {
                    companyLogo: '/images/aws.png',
                    tenure: 'Apr 2015 - Apr 2017',
                    position: 'Research and Development Engineer',
                    role: 'Responsible for POC(proof of concept) projects for mobile and web application'
                }
            ]
        }
    }
})
</script>