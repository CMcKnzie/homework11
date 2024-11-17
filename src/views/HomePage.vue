<script setup>
import {onMounted} from  'vue'
import MainCards from '@/components/MainCards.vue'
import MainPaigination from '@/components/MainPaigination.vue';
import useAPI from '@/composables/useAPI'; 

const { getEmployees, loading } = useAPI()

onMounted(async () => {
  await getEmployees()
})

</script>

<template>
  <p style ="text-align: center;" v-if ="loading">LOADING</p>
    <div v-else>
      <MainCards></MainCards>
      <MainPaigination></MainPaigination>
    </div>

</template>
