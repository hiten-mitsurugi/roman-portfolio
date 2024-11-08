<template >
    <section class="text-white mt-20" id="testimonials" data-aos="zoom-in">
        <h2 class="text-4xl font-bold text-white text-left mb-4 px-4 xl:pl-16">Testimonials</h2>
        <div class="px-4 xl:px-16">
            <Carousel v-bind="settings" :breakpoints="breakpoints" >
                <Slide v-for="element in testimonials" :key="element.id">
                    <div class="carousel__item p-4">
                        <div class="w-full mx-auto bg-[#111a3e] shadow-lg border border-[#1f1641] p-5 text-white font-light mb-6">
                            <div class="w-full flex mb-4 items-center">
                                <div class="overflow-hidden rounded-full w-10 h-10 bg-gray-50 border border-gray-200">
                                    <img :src="element.image" alt="testimonial image" loading="lazy">
                                </div>
                                <h6 class="ml-4 font-bold text-sm uppercase text-white">{{ element.fullName }}</h6>
                            </div>
                            <div class="w-full">
                                <p class="text-sm leading-tight">
                                    <span class="text-lg leading-none italic font-bold text-white mr-1">"</span>
                                        {{ element.comment }}
                                    <span class="text-lg leading-none italic font-bold text-white mr-1">"</span>
                                </p>
                            </div>
                        </div>
                    </div>
                </Slide> 
                <template #addons>
                    <Navigation />
                </template>
            </Carousel>
        </div>
    </section>
</template>
<script setup>
import { ref } from 'vue';
import { Carousel , Navigation , Slide } from 'vue3-carousel';
import 'vue3-carousel/dist/carousel.css';
//Carousel settings
const settings =ref({
    itemsToShow:1,
    snapAlign:"center",
})

//Breakpoints
const breakpoints =ref({
    700:{
        itemsToShow:2.5,
        snapAlign:'center',
    },
    1024:{
        itemsToShow:3,
        snapAlign:'start'
    }
})

const testimonials=ref([
{
    id: 1,
    fullName: 'client 1',
    image: '/src/assets/image.png',
    comment: 'Your work has truly exceeded my expectations! The quality and attention to detail are remarkable. I’m incredibly pleased with the outcome and would highly recommend your services.'
},
{
    id: 2,
    fullName: 'client 2',
    image: '/src/assets/image.png',
    comment: 'From start to finish, you were professional, timely, and highly skilled. Thank you for bringing my vision to life so perfectly. I look forward to working together again soon!'
},
{
    id: 3,
    fullName: 'client 3',
    image: '/src/assets/image.png',
    comment: 'Working with you has been a seamless experience. You handled every challenge with ease and delivered exactly what I needed. Thank you for your hard work!'
},
{
    id: 4,
    fullName: 'client 4',
    image: '/src/assets/image.png',
    comment: 'I couldn’t be happier with the results. You made the whole process smooth and enjoyable, and the final product was exactly what I had envisioned. Highly recommended!'
},
{
    id: 5,
    fullName: 'client 5',
    image: '/src/assets/image.png',
    comment: 'Your dedication to perfection is evident in the final result. Thank you for your incredible work ethic and commitment. It’s been a pleasure working with you!'
},
{
    id: 6,
    fullName: 'client 6',
    image: '/src/assets/image.png',
    comment: 'I’m so impressed by your creativity and attention to detail. You took my project to a level beyond what I imagined. I’m grateful for your hard work and talent!'
},
{
    id: 7,
    fullName: 'client 7',
    image: '/src/assets/image.png',
    comment: 'You made the entire process simple and enjoyable. I’m thrilled with the quality of your work and how well you understood my needs. Thank you for everything!'
},
{
    id: 8,
    fullName: 'client 8',
    image: '/src/assets/image.png',
    comment: 'Exceptional work and attention to detail! Your dedication to excellence is evident, and the end result speaks for itself. Thank you for making this experience so positive!'
},
{
    id: 9,
    fullName: 'client 9',
    image: '/src/assets/image.png',
    comment: 'You exceeded my expectations in every way! Your expertise and commitment to quality are evident, and I’m beyond pleased with the outcome. Thank you for a job well done!'
},
{
    id: 10,
    fullName: 'client 10',
    image: '/src/assets/image.png',
    comment: 'It’s rare to find someone who combines such talent with a deep understanding of client needs. You delivered exceptional results that I’m proud to showcase. Thank you!'
}

])
</script>
<style >
    .carousel__prev,.carousel__next {
        color: white !important;
    }
</style>