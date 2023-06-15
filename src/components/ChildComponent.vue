<template>
  <div>
    <p>{{ message }}</p>
    <button class="bg-blue-100 border rounded-md p-4" @click="emitEvent">Emit Event to Parent</button>
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