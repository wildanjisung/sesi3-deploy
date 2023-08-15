<template>
  <div class="about">
    <h1>This is an about page</h1>
    <h1>nilai store: {{ getAngkaFromStore }}</h1>
    <input type="number" v-model="inputAngka">
    <button @click="changeAngka">ganti angka</button>
  </div>
</template>

<script>
export default {
  name: "AboutView",
  data() {
    return {
      inputAngka: 0
    }
  },
  computed: {
    getAngkaFromStore() {
      return this.$store.state.about.angka
    }
  },
  methods: {
    changeAngka() {
      // this.$store.commit("setAngka", 80)
      this.$store.dispatch("about/checkValueAngka", this.inputAngka)
    }
  }
}
</script>
