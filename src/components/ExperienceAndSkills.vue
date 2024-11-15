<template>
    <section class="text-white mt-18" id="skills">
        <div class="absolute right-0 top-[110rem] h-full w-full justify-end">
            <span class="flex opacity-20">
                <span class="w-16 h-32 rounded-l-full flex bg-primary blur-2xl"></span>
                <span class="w-16 h-32 rounded-r-full flex bg-[#f88fc2] blur-2xl mt-14"></span>
            </span>
        </div>
        <div class="md:grid md:grid-cols-2 gap-8 items-center py-8 px-4 xl:gap-16 xl:px-16">
            <div class="mt-4 md:mt-0 text-left flex flex-col z-10 h-full w-[80%]">
                <h2 class="text-4xl font-bold text-white text-left mb-4">My 
                    <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">Skills</span>
                </h2>
                <div class="mt-8" v-for="skill in Skills" :key="skill.id">
                    <div class="flex items-end justify-between" data-aos="fade-right">
                        <h4 class="font-semibold uppercase text-white">
                            {{ skill.name }}
                        </h4>
                    </div>
                    <div class="mt-2 h-1 w-full bg-[#131d30] rounded-full">
                        <div class="h-1 rounded-full bg-primary" :style="`width :${skill.width}`"></div>
                    </div>
                </div>
            </div>
            <div data-aos="flip-left">
                <h2 class="text-4xl font-bold text-white text-left mb-8 md:text-center md:mt-0 mt-8">My Experiences</h2>
                <div class="space-y-8 py-8" data-aos="fade-left">
                    <div v-for="element in Experinces" :key="element.id"
                    class="flex  items-center rounded-xl p-4 bg-[#111a3e] shadow-lg border border-[#1f1641]"
                    >
                    <div class="w-1/4">
                        <img src="https://img.icons8.com/ios-filled/100/ffffff/lawyer.png" alt="lawyer">
                    </div>
                    <div class="w-3/4 pl-4">
                        <h3 class="text-2xl font-semibold uppercase text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">
                            {{ element.role }}
                        </h3>
                        <p class="text-white">{{ element.company }}</p>
                        <p class="text-white">{{ element.date }}</p>
                    </div>
                </div>
                </div>
            </div>
        </div>
    </section>
</template>
<script setup>
import { ref } from 'vue';
const Skills =ref([
    {
        id:1,
        name:'HTmL & CSS & JS',
        width:'98%'
    },
    {
        id:2,
        name:'Python',
        width:'75%'
    },
    {
        id:3,
        name:'PHP',
        width:'85%'
    },
    {
        id:4,
        name:'React & Vue & Angular',
        width:'88%'
    },
    {
        id:5,
        name:'Laravel & CI & Wordpress',
        width:'81%'
    },
    {
        id:6,
        name:'Django & Flask',
        width:'70%'
    },
    {
        id:7,
        name:'Markdown Editors',
        width:'75%'
    },
    {
        id:8,
        name:'React Native',
        width:'91%'
    },
    {
        id:9,
        name:'Flutter',
        width:'85%'
    },
    {
        id:10,
        name:'AWS & Azure & GCP & Docker',
        width:'92%'
    },
    {
        id:11,
        name:'Navicat Premium & Mongodb',
        width:'98%'
    },
    {
        id:12,
        name:'figma & Adobe XD',
        width:'91%'
    },
    {
        id:13,
        name:'Web Scrapy',
        width:'68%'
    },
    {
        id:14,
        name:'Blender',
        width:'70%'
    },
]);

const Experinces =ref([
    {
        id:1,
        role:'Freelancer',
        company:'Upwork',
        date:'October 2024- November 2024'
    },
    {
        id:2,
        role:'Senior Blockchain developer',
        company:'Gihot',
        date:'October 2021 - November 2023'
    },
    {
        id:3,
        role:'Web3 developer',
        company:'Orient Software',
        date:'February 2020 - September 2021'
    },
    {
        id:4,
        role:'Full Stack Developer',
        company:'RECentral',
        date:'September 2016 - July 2019'
    },
    {
        id:5,
        role:'Backend Developer',
        company:'Bytes Software Services',
        date:'October 2014 - March 2016'
    },
])
</script>
