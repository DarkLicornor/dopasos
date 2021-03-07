<template>
  <div class="tile">
    <div class="icon">
        <img :src="require(`@/assets/icons/${icon}`)" />
    </div>
    <div class="amount-tile">
        <p class=""> {{amount}} </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ActivityDetail',
  props: {
    amount: String,
    icon: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.tile {
    background: #FDF7FF;
    border-radius: 25px;
    width: 150px;
    height: 200px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin: 16px;
}
img {
    color: #FFBA43;
    width: 50px;
    height: 50px;
}

.icon {
    height: 100px;
    width: 150px;
    height: 100px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    color: #FDF7FF;
}

.amount-tile {
    background: #FFBA43;
    border-radius: 0px 0px 25px 25px;
    width: 150px;
    height: 100px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;

    color: #FDF7FF;
    font-size: 52px;
}

</style>
