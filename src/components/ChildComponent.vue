<template>
  <div>
    <p>{{ message }}</p>
    <button @click="emitEvent">Emit Event to Parent</button>
  </div>
</template>

<script>
export default {
  props: ['message'],
  methods: {
    emitEvent() {
      this.$emit('child-event', 'Hello from child component');
    }
  }
}
</script>