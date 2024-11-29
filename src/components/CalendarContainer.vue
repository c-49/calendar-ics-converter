<template>
  <div class="full-width text-white" style="height:60vh">
    <q-date v-model="dates" landscape dark today-btn multiple class="fit" mask="MM/DD/YYYY" />
    <q-btn color="primary" label="Generate" no-caps @click="generateCalendar" />
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue'
import { ics } from './ics'
export default defineComponent({
  name: 'CalendarContainer',
  setup() {
    const dates = ref([])
    const generateCalendar = () => {
      const cal = ics()
      dates.value.forEach(d => {
        cal.addEvent('Work', '', '', d, d)
      })
      cal.download('Work Events')
    }
    return {
      dates,
      generateCalendar
    }
  }
})
</script>

<style></style>
