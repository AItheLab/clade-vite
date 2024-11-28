<script setup lang="ts">
import { ref } from 'vue'
import ReservationCalendar from './components/reservation/ReservationCalendar.vue'
import ReservationList from './components/reservation/ReservationList.vue'
import ReservationDialog from './components/reservation/ReservationDialog.vue'

const showNewReservation = ref(false)
const reservations = ref([
  {
    id: 1,
    date: new Date(),
    time: '10:00',
    name: 'John Doe',
    email: 'john@example.com',
    status: 'Confirmada'
  }
])
</script>

<template>
  <div class="container mx-auto py-8">
    <h1 class="text-3xl font-bold mb-8">Sistema de Reservas</h1>
    
    <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
      <ReservationCalendar @new-reservation="showNewReservation = true" />
      <ReservationList :reservations="reservations" />
    </div>

    <ReservationDialog
      v-model:open="showNewReservation"
    />
  </div>
</template>