<template >
    <section class="text-white mt-20" id="services">
        <div class="px-4 xl:pl-16">
            <h2 class="text-4xl font-bold text-white mb-4">My Services</h2>
        </div>
        <div class="py-8 xl:px-16 px-4 sm:py-16 grid grid-cols-1 gap-6 pt-10 sm:grid-cols-2 md:gap-10 md:pt-12 lg:grid-cols-3">
            <div v-for="service in services" :key="service.id" data-aos="fade-up"
            class="px-8 py-12 rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641]"
            >
                <div class="mx-auto h-24 w-24 text-center xl:h-28 xl:w-28">
                    <div>
                        <img :src="service.icon" alt="service icon">
                    </div>
                </div>
                <div class="text-center">
                    <h3 class="pt-8 text-lg font-semibold uppercase text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary lg:text-xl">
                        {{ service.name }}
                    </h3>
                    <p class="text-grey pt-4 text-sm group-hover:text-white md:text-base">
                        {{ service.description }}
                    </p>
                </div>
            </div>
        </div>
    </section>
</template>
<script setup>
import {ref} from 'vue';
const services =ref([
    {
        id:1,
        icon:'src/assets/icons/web_96px.png',
        name:'WEB DEVELOPMENT',
        description:'Building responsive, user-friendly websites using modern technologies like HTML, CSS, JavaScript, and frameworks such as React, Vue.js and Angular.'
    },
    {
        id:2,
        icon:'src/assets/icons/documents_96px.png',
        name:'Technical Writing',
        description:'Crafting clear, concise documentation, user guides, and technical content to simplify complex concepts for developers and end-users.'
    },
    {
        id:3,
        icon:'src/assets/icons/mobile_96px.png',
        name:'Mobile Development',
        description:'Creating intuitive and high-performance mobile apps for iOS and Android using frameworks like React Native or Flutter.'
    },
    {
        id:4,
        icon:'src/assets/icons/docker_96px.png',
        name:'Containerization',
        description:'Streamlining software development and deployment processes by automating workflows, managing cloud infrastructure, and ensuring system reliability.'
    },
    {
        id:5,
        icon:'src/assets/icons/database_administrator_96px.png',
        name:'Database Administration',
        description:'Designing, managing, and optimizing databases for performance, security, and scalability, with expertise in SQL and NoSQL systems.'
    },
    {
        id:6,
        icon:'src/assets/icons/figma_96px.png',
        name:'Web Design',
        description:'Designing visually engaging, user-centered websites and interfaces with a focus on aesthetics, functionality, and responsive layouts.'
    },
    ])
</script>

