<template>
    <section class="text-white mt-20" id="projects">
        <div class="px-4 xl:pl-16">
            <div class="mb-4 md:flex md:justify-between xl:pr-16">
                <h2 class="text-4xl font-bold text-white"> My Latest Projects</h2>
                <div class="flex space-x-4 mb-4 mt-5 md:mt-0">
                    <button class="hover:text-primary" v-for="category in ['All', 'Web development', 'Blockchain development','Data scrapy','Mobile App']"
                        :key="category" @click="() => selectedCategory = category">
                        {{ category }}
                    </button>
                </div>
            </div>
            <ul class="px-4 sm:py-16 xl:pr-16 grid grid-cols-1 gap-6 pt-10 sm:grid-cols-2 md:gap-10 md:pt-12 lg:grid-cols-3"
                data-aos="fade-right">
                <div v-for="project in filteredProjects" :key="project.id">
                    <div class="h-52 md:h-[24rem] rounded-t-xl relative group"
                    :style="{ backgroundImage: 'url(' + project.image + ')', backgroundSize: 'cover' }">                    
                    <div class="overlay items-center justify-center absolute top-0 left-0 w-full h-full bg-[#181818] bg-opacity-0
                    hidden group-hover:flex group-hover:bg-opacity-80 transition-all duration-500
                    ">
                        <a class="h-14 w-14 mr-2 border-2 relative rounded-full border-[#ADB7BE] hover:border-white group/link"
                            :href="project.gitURL"> <svg xmlns="http://www.w3.org/2000/svg" fill="none"
                                viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true"
                                data-slot="icon"
                                class="h-10 w-10 text-[#ADB7BE] absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2  cursor-pointer group-hover/link:text-white">
                                <path stroke-linecap="round" stroke-linejoin="round"
                                    d="M17.25 6.75 22.5 12l-5.25 5.25m-10.5 0L1.5 12l5.25-5.25m7.5-3-4.5 16.5">
                                </path>
                            </svg></a><a
                            class="h-14 w-14 border-2 relative rounded-full border-[#ADB7BE] hover:border-white group/link"
                            :href="project.webURL"> <svg xmlns="http://www.w3.org/2000/svg" fill="none"
                                viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true"
                                data-slot="icon"
                                class="h-10 w-10 text-[#ADB7BE] absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2  cursor-pointer group-hover/link:text-white">
                                <path stroke-linecap="round" stroke-linejoin="round"
                                    d="M2.036 12.322a1.012 1.012 0 0 1 0-.639C3.423 7.51 7.36 4.5 12 4.5c4.638 0 8.573 3.007 9.963 7.178.07.207.07.431 0 .639C20.577 16.49 16.64 19.5 12 19.5c-4.638 0-8.573-3.007-9.963-7.178Z">
                                </path>
                                <path stroke-linecap="round" stroke-linejoin="round"
                                    d="M15 12a3 3 0 1 1-6 0 3 3 0 0 1 6 0Z"></path>
                            </svg></a>
                    </div>
                </div>
                <div class="text-white rounded-b-xl mt-3 bg-[#111a3e] shadow-lg border border-[#1f1641] py-6 px-4">
                    <h3 class="text-lg font-semibold uppercase lg:text-xl"> {{ project.title }}</h3>
                    <p class="text-[#ADB7BE]">{{ project.description }}</p>
                    <div class="flex flex-wrap p-2.5">
                        <div v-for="technology in project.technologies" :key="technology" class="text-center ml-1 mt-1 rounded-3xl bg-[#111827]"
                        style="box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1); border: 1px solid #111827;backdrop-filter: blur(9px);-webkit-backdrop-filter: blur(9px);"
                        >
                    <p class="px-1 py-2">{{ technology }}</p>
                    </div>
                    </div>
                </div>
                </div>
            </ul>
        </div>
    </section>
</template>
<script setup>
import { ref, computed } from 'vue';

const Projects = ref([
    {
        id: 1,
        category: 'Web development',
        image: 'src/assets/projects/portfolio-vue.png',
        title: 'Personal Portfolio with Vue3',
        description: 'Designed and developed a personal portfolio website to showcase my skills, projects, and professional journey. The website is responsive and built using HTML, CSS, and JavaScript, featuring smooth animations and a user-friendly layout.',
        technologies: ['vue.js 3', 'vite', 'Tailwind', 'vue3-carousel', 'aos'],
        gitURL: 'https://github.com/high5dev/portfolio-vue',
        webURL: 'https://dinhthang-vue.vercel.app/'
    },
    {
        id: 2,
        category: 'Web development',
        image: 'src/assets/projects/3D_portfolio.png',
        title: '3D Portfolio Showcase Website',
        description: 'Developed an innovative 3D portfolio showcase website using Three.js to create immersive 3D environments. The website allows users to explore projects in a visually engaging manner, providing an interactive experience.',
        technologies: ['Three.js', 'React', 'CSS', 'Tailwind', 'Vite', 'Blender'],
        gitURL: 'https://github.com/high5dev/3d-portfolio-1st',
        webURL: 'https://dinhthang-3d.vercel.app/'
    },
    {
        id: 3,
        category: 'Data scrapy',
        image: 'src/assets/projects/scrapper-amazon.png',
        title: 'Amazon Product Scrapper',
        description: 'Scraping Amazon Product Pages: The scraper extracts various product details from Amazon, including title, brand, specs, and features. Windows Executable no to run script file, Scrapped data saving in CSV and PDF. Gracefully handliing errors and warnings.',
        technologies: ['Python', 'Beautifulsoup', 'tkinter', 'reportlab', 'urllib3', 'Pillow'],
        gitURL: 'https://github.com/high5dev/amazon-scrapper-tkinter',
        webURL: ''
    },
    {
        id: 4,
        category: 'Blockchain development',
        image: 'src/assets/projects/NFT-marketplace.png',
        title: 'NFT Marketplace',
        description: 'Created a marketplace for non-fungible tokens (NFTs) where users can mint, buy, and sell digital assets. Integrated payment processing for crypto transactions and implemented user authentication. The software architecture is MERN stack.',
        technologies: ['React', 'Node.js', 'MongoDB', 'Soidity', 'CSS'],
        gitURL: '',
        webURL: ''
    },
    {
        id: 5,
        category: 'Web development',
        image: 'src/assets/projects/E-Commerce.png',
        title: 'E-Commerce Web Application',
        description: 'Developed a robust e-commerce platform using Angular for the front end and Laravel for the back end. Implemented features like product management, user authentication, and payment processing to create a seamless shopping experience.',
        technologies: ['Angular', 'Laravel', 'MySQL', 'RESTful API', 'DB Architecture'],
        gitURL: '',
        webURL: ''
    },
    {
        id: 6,
        category: 'Mobile App',
        image: '@/assets/projects/mobile.jpg',
        title: 'E-commerce app',
        description: 'Developed a cross-platform e-commerce app that allows users to browse products, make purchases, and track orders. Payment processing with Stripe and Firebase for real-time data syncing. Built custom UI components to enhance user experience and improve app performance.',
        technologies: ['Figma', 'React Native', 'Flutter', 'Swift', 'Stripe', 'Google Maps API'],
        gitURL: '',
        webURL: ''
    }
]);

const selectedCategory = ref('All');
const filteredProjects = computed(() => {
    if (selectedCategory.value === 'All') {
        return Projects.value;
    }
    return Projects.value.filter(project => project.category.toLocaleLowerCase() === selectedCategory.value.toLocaleLowerCase());
})

</script>
