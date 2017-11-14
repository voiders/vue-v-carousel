<template>
  <section class="hero is-primary is-large">
    <div class="hero-body">
      <div class="container">
        <h1 class="title">
        {{msg}}
        </h1>
        <h2 class="subtitle">
        Medium subtitle
        </h2>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'carousel',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<style src="bulma/css/bulma.css"></style>
