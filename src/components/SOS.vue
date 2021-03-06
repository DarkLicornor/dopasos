<template>
  <div class="sos">
    <p> sos component </p>
    <div class="sos-layout">
      <h1>DopaSOS</h1>
      <Button class="bigButton" v-on:click="getActivity()" smallText="Give me anything to do." bigText="Anything, really"/>
      <div class="sos-choices">
        <Button class="smallButton" v-on:click="getActivity('home improvement')" icon="home.svg" />
        <Button class="smallButton" v-on:click="getActivity('self improvement')" icon="heart.svg" />
        <Button class="smallButton" v-on:click="getActivity('chore')" icon="chore.svg" />
      </div>
      <div v-if="dopactivity.summary">
        <h1> {{dopactivity.summary}} </h1>
      </div>
    </div>
  </div>
</template>

<script>
import json from '@/assets/data.json'
import Button from './atoms/Button'

export default {
  data () {
    return {
      myJson: json,
      activities: json.activities,
      dopactivity: {}
    }
  },
  name: 'SOS',
  components: {
    Button
  },
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

.sos-layout {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
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

.bigButton {
  width: 300px;
  height: 300px;
  color: #4C0BB7;
}

.smallButton {
  width: 150px;
  height: 150px;
  color: #4C0BB7;
}
</style>
