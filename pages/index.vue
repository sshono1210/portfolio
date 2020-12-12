<template>
  <div class="container">
    <div>
      hoge
    </div>
  </div>
</template>

<script>
export default {
  async mounted() {
    console.log(process.env.HELLO)
    this.$axios.defaults.headers.common['Authorization'] = 'token ' + process.env.API_KEY
    const response = await this.$axios.$get('https://api.github.com/user/repos?per_page=100')
    console.log(response)
  }
}
</script>

<style>
</style>
