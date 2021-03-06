<template>
  <div class="sos">
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
@import url('https://fonts.googleapis.com/css2?family=Beth+Ellen&display=swap');
.sos {
  position: fixed;
  width: 100vw;
  height: 100vh;
  background-image: linear-gradient(to right top,
    #4c0bb7,
    #7100b0,
    #8b00a9,
    #a000a3,
    #b2009c,
    #d2008e,
    #ea1e7f,
    #fc3c70,
    #ff6e59,
    #ff9f4b,
    #ffcd51,
    #f9f871);

    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

h1 {
  font-family: Beth Ellen;
  font-style: normal;
  font-weight: normal;
  font-size: 72px;
  line-height: 48px;
  color: #FDF7FF;
  margin-bottom: 72px
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
  width: 290px;
  height: 290px;
  color: #4C0BB7;
}

.smallButton {
  width: 150px;
  height: 150px;
  color: #4C0BB7;
}
</style>
