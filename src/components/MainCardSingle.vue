<script setup>
import { faker } from '@faker-js/faker'

const props = defineProps({
    employee: {
        type: Object,
        required: true,
        default: () => {
            return {
                _id: "65f1b471c1d4a06a0786c3bc",
                userName: "jperez",
                firstName: "Joseph",
                lastName: "Perez",
                title: "Computer Science Wizard",
                quote: "You shall not pass!",
                __v: 0,
            }
        }
    },
})
</script>

<template>
  <!-- {{ fullname }} <br /> -->
  <RouterLink :to="{name: 'CardDetails', params: {id: props.employee.use._id}}">
    <div class="border border-gray-400 rounded-xl shadow bg-gray-200 h-full">
      <img :src="faker.image.urlLoremFlickr({category: 'cat'})" class="rounded-t-xl" />
      <div class="p-4">
        <p class="mb-2 text-2xl font-bold">{{ props.employee_firstName }} {{ props.employee.lastName }}</p>
        <p class="mb-3 font-normal text-gray-700">{{ props.employee.title }}</p>
        <p class="mb-3 font-normal text-gray-700">{{ props.employee.quote }}</p>
      </div>
    </div>
  </RouterLink>
</template>
