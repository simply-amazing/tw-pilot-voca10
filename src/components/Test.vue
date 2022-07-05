<template>
  <h1>{{ msg }}</h1>
  <button @click="count++">count is: {{ count }}</button>
  <p>Edit <code>components/HelloWorld.vue</code> to test hsadasdasdasot module replacement.</p>


</template>

<script>
export default {
  name: 'Test',
  props: {
    msg: String
  },
  data() {
    return {
      count: 0
    }
  }
}
</script>
