<template>
  <div v-if="dopactivity.summary" class="activity">
    <p> activity component </p>
    <div>
      <h1> {{dopactivity.summary}} </h1>
    </div>
    <div class="activity-actions">
      <div class="activity-tile" id="activity-reward-info">
        <p>TODO iterate over all rewards</p>
      </div>
      <div class="activity-tile" id="activity-done-button">
        <p> Did it ! </p>
      </div>
      <div class="activity-tile" id="activity-cantdo-button">
        <p>Can't do..</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SOS',
  props: {
    msg: String,
    dopactivity: Object
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

.activity {
  background: red;
}

.activity-actions {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-around;
}
</style>
