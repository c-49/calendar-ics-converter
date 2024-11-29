<template>
  <q-page class="flex flex-center bg-dark">
    <calendar-container />
  </q-page>
</template>

<script>
import CalendarContainer from 'src/components/CalendarContainer.vue'
import { defineComponent } from 'vue'
export default defineComponent({
  name: 'PageIndex',
  components: { CalendarContainer }
})
</script>
