<template>
  <div class="home">
    <SOS v-on:dopactivity="updateDopactivity" msg="Welcome to Your Vue.js App"/>
    <Activity v-if="Object.keys(dopactivity).length !== 0"  :dopactivity="dopactivity" />
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
      this.dopactivity = newActivity
    }
  }
}
</script>
