<script setup>

import { faker } from '@faker-js/faker'
import { RouterLink } from 'vue-router'

const props = defineProps({

    employee: {
        type: Object, 
        required: true, 
        default: () => {
            return {
                _id: "6730f937d8e95423aa1b7f33",
                userName: "cmckenzie",
                firstName: "Caitlyn",
                lastName: "McKenzie",
                title: "Student",
                quote: "If I had a flower for every time I thought of you...I could walk through my garden forever.",
                __v: 0,
            }
        },
    },
})


</script>

<template>
     <RouterLink :to="{name: 'CardDetails', params: {id:props.employee._id}}">
    <div class="border border-gray-400 rounded-lg shadow bg-gray200 h-full">
        <img :src="faker.image.urlLoremFlickr({width: 640, height: 480, category: 'person'})" class="rounded-t-xl"/>

    <div class="p-4">
        <p class="mb-2 text-2xl font-bold">{{ props.employee.firstName}} {{ props.employee.lastName}}</p>
        <p class="mb-3 text-gray-700 font-normal">{{ props.employee.title}}</p>
        <p class="mb-3 text-gray-700 font-normal"> {{ props.employee.quote }}</p>
    </div>
</div>
     </RouterLink>
</template>