<template>
  <h1>The reuslt is {{score}}ms</h1>
  <div v-if="score<250">
    <p>wow you are thunder speed</p>
  </div>
  <div v-else-if="score>250 && score<500">You click at a normal speed</div>
  <div v-else-if="score > 500">you are so slow</div>
</template>

<script>
export default {
    props:['score']
}
</script>

<style>

</style>