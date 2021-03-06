<template>
  <div class="button" v-on:click="$emit('clicked', tag)">
      <img v-if='icon' :src="require(`@/assets/icons/${icon}`)" />
      <p class="smallText" v-if='smallText'> {{smallText}} </p>
      <p class="bigText" v-if='bigText'> {{bigText}} </p>
  </div>
</template>

<script>
export default {
  name: 'Button',
  props: {
    smallText: String,
    bigText: String,
    icon: String,
    tag: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.button {
    background: #FDF7FF;
    box-shadow: 0px 0px 10px 10px rgba(76, 11, 183, 0.2);
    border-radius: 50%;
    width: 300px;
    height: 300px;

    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: all 0.1s linear;

}

.button:hover{
    box-shadow: inset 0px 0px 5px 1px rgba(76, 11, 183, 0.2);
    transform: scale(1.05)
}

img {
    width: 50px;
    height: 50px;
}
.smallText {
    margin: 0;
}

.bigText {
    font-size: 36px;
    margin: 2px;
}
</style>
