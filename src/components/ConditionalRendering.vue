<script>
export default {
  data() {
    return {
        awesome: true,
        ok: true,
    };
  },
  methods: {

  }
};
</script>

<template>

    <button @click="awesome = !awesome">Toggle</button>

    <h1 v-if="awesome">Vue is awesome!</h1>
    <h1 v-else>Oh no 😢</h1>

    <hr>

    <template v-if="ok">
    <h1>Title</h1>
    <p>Paragraph 1</p>
    <p>Paragraph 2</p>
    </template>

    <hr>

    <h1 v-show="ok">Hello Show!</h1>

</template>

<style scoped>

</style>
