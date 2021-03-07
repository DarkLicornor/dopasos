<template>
  <div v-if="dopactivity.summary" class="activity">
    <div>
      <h1> {{dopactivity.summary}} </h1>
    </div>
    <div class="activity-actions">
      <ActivityDetail icon="clock.svg" amount="5"/>
      <ActivityDetail icon="chore.svg" amount="10"/>
      <ActivityDetail icon="heart.svg" amount="0"/>
      <ActivityDetail icon="home.svg" amount="0"/>
    </div>
    <div class="activity-followup">
      <Button class="smallButton" id="nope" smallText="Can't do" v-on:clicked="goBackToSos" />
      <Button class="smallButton" id="done" smallText="Done" v-on:clicked="goBackToSos" />
    </div>
  </div>
</template>

<script>
import ActivityDetail from '@/components/atoms/ActivityDetail.vue'
import Button from '@/components/atoms/Button.vue'
export default {
  name: 'SOS',
  props: {
    msg: String,
    dopactivity: Object
  },
  components: {
    ActivityDetail,
    Button
  },
  methods: {
    goBackToSos: function () {
      this.$emit('updateDopactivity', {})
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Beth+Ellen&display=swap');

h1 {
  font-family: Beth Ellen;
  color: #FDF7FF;
}
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

.activity {
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

.activity-actions {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-around;
}

.activity-followup {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-around;
  margin-top: 64px;
}

.smallButton {
  width: 150px;
  height: 150px;
  color: #FDF7FF;
  margin: 16px;
}

#nope {
  background: #FF066A;
}

#done {
  background: #479F90;
}
</style>
