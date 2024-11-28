<script setup lang="ts">
import { Button } from '@/components/ui/button'
import { Input } from '@/components/ui/input'
import { Calendar } from '@/components/ui/calendar'
import { ref } from 'vue'

const name = ref('')
const email = ref('')
const date = ref<Date | undefined>(new Date())
const time = ref('')
const notes = ref('')

const handleSubmit = () => {
  // TODO: Implementar lógica de envío
  console.log({ name: name.value, email: email.value, date: date.value, time: time.value, notes: notes.value })
}
</script>

<template>
  <form @submit.prevent="handleSubmit" class="space-y-4 p-4">
    <div class="space-y-2">
      <label for="name" class="text-sm font-medium">Nombre</label>
      <Input id="name" v-model="name" required />
    </div>

    <div class="space-y-2">
      <label for="email" class="text-sm font-medium">Email</label>
      <Input id="email" type="email" v-model="email" required />
    </div>

    <div class="space-y-2">
      <label class="text-sm font-medium">Fecha</label>
      <Calendar v-model="date" class="rounded-md border" />
    </div>

    <div class="space-y-2">
      <label for="time" class="text-sm font-medium">Hora</label>
      <Input id="time" type="time" v-model="time" required />
    </div>

    <div class="space-y-2">
      <label for="notes" class="text-sm font-medium">Notas</label>
      <Input id="notes" v-model="notes" />
    </div>

    <Button type="submit" class="w-full">Crear Reserva</Button>
  </form>
</template>