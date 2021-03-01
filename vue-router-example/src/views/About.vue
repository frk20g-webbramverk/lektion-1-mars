<template>
  <div class="about">
    <h1>This is an about page about {{ name }}</h1>
  </div>
</template>

<script>
export default {
  computed: {
    name() {
      return this.$route.params.name
    }
  }
}
</script>

<style>

</style>