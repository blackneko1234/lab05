<template>
  <div id="flashMessage" v-if="GStore.flashEdit">
    {{ GStore.flashEdit }}
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
