<template>
  <div class="home">
    <SOS v-if="Object.keys(dopactivity).length === 0" v-on:updateDopactivity="updateDopactivity"/>
    <Activity v-if="Object.keys(dopactivity).length !== 0" :dopactivity="dopactivity" v-on:updateDopactivity="updateDopactivity"/>
  </div>
</template>

<script>
// @ is an alias to /src
import SOS from '@/components/SOS.vue'
import Activity from '../components/Activity.vue'

export default {
  name: 'Home',
  components: {
    SOS,
    Activity
  },
  data () {
    return {
      dopactivity: {}
    }
  },
  methods: {
    updateDopactivity: function (newActivity) {
      console.log('updated!')
      this.dopactivity = newActivity
    }
  }
}
</script>

<style scoped lang="scss">
</style>
