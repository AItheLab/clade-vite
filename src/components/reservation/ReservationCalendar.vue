<script setup lang="ts">
import { Calendar } from '@/components/ui/calendar'
import { Button } from '@/components/ui/button'
import { ref } from 'vue'

const date = ref<Date | undefined>(new Date())
</script>

<template>
  <div class="flex flex-col space-y-4 p-4">
    <div class="flex justify-between items-center">
      <h2 class="text-2xl font-bold">Calendario de Reservas</h2>
      <Button @click="$emit('new-reservation')">Nueva Reserva</Button>
    </div>
    
    <Calendar
      v-model="date"
      class="rounded-md border"
    />
  </div>
</template>