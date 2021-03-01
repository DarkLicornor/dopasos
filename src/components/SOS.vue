<template>
  <div class="sos">
    <p> sos component </p>
    <div>
      <h1>I need help now. Give me something to do!</h1>
      <div class="sos-choices">
        <div class="sos-choice" v-on:click="getActivity('home improvement')"> Give me Home improvement stuff</div>
        <div class="sos-choice" v-on:click="getActivity('self improvement')"> Give me Self improvement stuff</div>
        <div class="sos-choice" v-on:click="getActivity()"> Give me ANYTHING</div>
      </div>
      <div v-if="dopactivity.summary">
        <h1> {{dopactivity.summary}} </h1>
      </div>
    </div>
  </div>
</template>

<script>
import json from '@/assets/data.json'
export default {
  data () {
    return {
      myJson: json,
      activities: json.activities,
      dopactivity: {}
    }
  },
  name: 'SOS',
  props: {
    msg: String
  },
  methods: {
    getActivity: function (tag) {
      const activityList = tag
        ? this.activities.filter(({ tags }) => tags.includes(tag))
        : this.activities
      const activity = activityList[Math.floor(Math.random() * activityList.length)]
      this.$emit('dopactivity', activity)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.sos {
  background: darkorange;
}
.sos-choices {
  display:flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-around;

  div {
    margin:2em;
    cursor:pointer;
    color: #42b983;
  }
}
</style>
