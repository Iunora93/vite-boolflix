<script>
import SectionMovie from '../components/SectionMovie.vue'
import SectionSeries from '../components/SectionSeries.vue'

export default {
  name: 'AppMain',
  components:{
    SectionMovie,
    SectionSeries,
  },
}
</script>

<template>
  <h2>MOVIE</h2>
  <SectionMovie />
  <h2>SERIE</h2>
  <SectionSeries />
</template>

<style>
</style>