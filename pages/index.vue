<template>
  <v-container fill-height>
    <v-container>
      <index-title />
      <yml-file />
    </v-container>
  </v-container>
</template>

<script lang="ts">
import Vue from 'vue'
import IndexTitle from '@/components/index/IndexTitle.vue'
import YmlFile from '@/components/index/YmlFile.vue'

export default Vue.extend({
  name: 'Index',

  components: {
    IndexTitle,
    YmlFile
  }
})
</script>

<style>
.vue-typer .custom.char.typed {
  font-size: 18px;
  color: #fff;
}

@media screen and (min-width: 500px) {
  .vue-typer .custom.char.typed {
    font-size: 24px;
  }
}

.vue-typer .custom.caret {
  display: none;
}
</style>
