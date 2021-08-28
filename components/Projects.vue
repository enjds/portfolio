<template>
    <section>
       <div class="flex w-full bg-white p-5 mb-4 rounded-xl">
           <h3 cla>Projects({{ projects.length }})</h3>
       </div>
       <div v-for="(project, index) in projects" v-bind:key="index" class="flex mb-10 w-full bg-white p-5 rounded-xl shadow-lg">
            <div class="h-72 w-80 bg-gray-200 mr-9 rounded-xl overflow-hidden">
                 <img class="h-full w-full object-cover" v-bind:src="project.imageUrl" />
            </div>
            <div class="flex flex-col justify-between flex-1">
                <div>
                    <ul>
                        <li class="inline mr-3" v-for="(tech, index) in project.technologies" v-bind:key="index">{{ '#' + tech }}</li>
                    </ul>
                    <h1 class="mt-6 mb-3">{{ project.name }}</h1>
                    <p class="mb-8 text-gray-400">{{ project.summary }}</p>
                </div>
               <div>
                   <button v-on:click="openLink(project.link)" class="bg-blue-600 text-white rounded-xl w-32 h-11 mr-3">Demo</button>
                   <button v-if="project.code" v-on:click="openLink(project.code)" class="border border-blue-600 text-blue-600 rounded-xl w-32 h-11">Code</button>
               </div>
            </div>
       </div>
    </section>
</template>

<style scoped>
    h1 {
        font-size: 24px;
        line-height: 29.26px;
        font-weight: 500;
    }

    h3 {
        font-size: 18px;
        line-height: 21.94px;
         font-weight: 500;
    }

    p {
        font-size: 16px;
        line-height: 19.5px;
    }
</style>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
     data: function() {
        return {
            projects: [
                {
                    imageUrl: '/projects/booknlive.jpeg',
                    technologies: ['CSS', 'HTML', 'responsive', 'Angular', 'Material Design'],
                    name: 'BookNLive',
                    link: 'https://www.booknlive.co/#/',
                    summary: 'In this project, I work with Angular and Material Design to create a responsive page. I did the architecture of the frontend code and worked on the map search feature similar to AirBnB'
                },
                 {
                    imageUrl: '/projects/mysunlifehk-portal.jpeg',
                    technologies: ['CSS', 'HTML', 'responsive', 'Angular', 'NGRX'],
                    name: 'My Sun Life HK',
                    link: 'https://mysunlife.sunlife.com.hk/ClientAppWeb/#/login',
                    summary: 'Architect of the frontend code, I did the optimization of the website performance to reach the rating ~85%. Main responsible for security assessment and best practices implementation'
                }
            ]
        }
    },
    methods: {
       openLink: function (link: string) {
           window.open(link)
       }
    }
})
</script>