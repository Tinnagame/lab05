<template>
  <p>Edit the event here</p>
  <button @click="edit">Click Me</button>
</template>

<script>
export default {
  props: ['event'],
  inject: ['GStore'],
  methods: {
    edit() {
      this.GStore.flashEditMessage = 'Data has been updated '
      setTimeout(() => {
        this.GStore.flashEditMessage = ''
      }, 3000)
      this.$router.push({
        name: 'EventDetails',
        params: { id: this.event.id }
      })
    }
  }
}
</script>
