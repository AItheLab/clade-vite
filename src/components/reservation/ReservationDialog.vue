<script setup lang="ts">
import { Dialog, DialogContent, DialogHeader, DialogTitle } from '@/components/ui/dialog'
import ReservationForm from './ReservationForm.vue'

defineProps<{
  open: boolean
}>()

defineEmits<{
  'update:open': [value: boolean]
}>()
</script>

<template>
  <Dialog :open="open" @update:open="$emit('update:open', $event)">
    <DialogContent class="sm:max-w-[425px]">
      <DialogHeader>
        <DialogTitle>Nueva Reserva</DialogTitle>
      </DialogHeader>
      <ReservationForm />
    </DialogContent>
  </Dialog>
</template>