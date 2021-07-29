<template>
  <p>Edit the event here</p>
  <button @click="edit">Edit Me</button>
</template>

<script>
export default {
  props: ['event'],
  inject: ['GStore'], //<--- Inject the Global store
  methods: {
    edit() {
      // Assuming successful API call to register them
      // Set a flash message to appear ono the next page loaded which says
      // 'You are successfully registered for ' + this.event.title
      this.GStore.flashEdit = 'The data has been updated'
      setTimeout(() => {
        // After 3 seconds remove it
        this.GStore.flashEdit = ''
      }, 3000)
      this.$router.push({
        name: 'EventDetails',
        params: { id: this.event.id }
      })
    }
  }
}
</script>
