<template>
  <h1 align="center">
    <client-only>
      <vue-typer
        text="Hello World!"
        erase-style="backspace"
        :erase-on-complete="true"
        :pre-erase-delay="300"
        :erase-delay="150"
        :repeat="0"
      ></vue-typer>
      <vue-typer
        text="Welcome to My portfolio page!"
        :repeat="0"
        :pre-type-delay="3500"
      ></vue-typer>
    </client-only>
  </h1>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexTitle'
})
</script>
