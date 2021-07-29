<template>
  <div id="flashEditMessage" v-if="GStore.flashEditMessage">
    {{ GStore.flashEditMessage }}
  </div>
  <p>{{ event.time }} on {{ event.date }} @ {{ event.location }}</p>
  <p>{{ event.description }}</p>
</template>

<script>
export default {
  props: ['event'],
  inject: ['GStore']
}
</script>
<style scoped>
@keyframes bluefade {
  from {
    background: blue;
  }
  to {
    background: transparent;
  }
}
#flashEditMessage {
  animation-name: bluefade;
  animation-duration: 3s;
}
</style>
