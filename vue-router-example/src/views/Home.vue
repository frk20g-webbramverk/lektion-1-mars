<template>
  <div class="home">
    <input type="text" placeholder="Ditt namn" v-model="name" />
    <button v-on:click="send">Skicka</button>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  data() {
    return {
      name: ''
    }
  },
  methods: {
    send: function() {
      console.log(this.$route);
      this.$router.push('/about/' + this.name);
    }
  }
}
</script>
