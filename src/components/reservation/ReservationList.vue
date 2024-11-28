<script setup lang="ts">
import {
  Table,
  TableBody,
  TableCell,
  TableHead,
  TableHeader,
  TableRow,
} from '@/components/ui/table'

// TODO: Tipado de reservas
defineProps<{
  reservations: any[]
}>()
</script>

<template>
  <div class="p-4">
    <h2 class="text-2xl font-bold mb-4">Lista de Reservas</h2>
    
    <Table>
      <TableHeader>
        <TableRow>
          <TableHead>Fecha</TableHead>
          <TableHead>Hora</TableHead>
          <TableHead>Nombre</TableHead>
          <TableHead>Email</TableHead>
          <TableHead>Estado</TableHead>
        </TableRow>
      </TableHeader>
      <TableBody>
        <TableRow v-for="reservation in reservations" :key="reservation.id">
          <TableCell>{{ new Date(reservation.date).toLocaleDateString() }}</TableCell>
          <TableCell>{{ reservation.time }}</TableCell>
          <TableCell>{{ reservation.name }}</TableCell>
          <TableCell>{{ reservation.email }}</TableCell>
          <TableCell>{{ reservation.status }}</TableCell>
        </TableRow>
      </TableBody>
    </Table>
  </div>
</template>