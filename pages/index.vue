<template>
  <v-container fill-height>
    <v-container>
      <index-title />
      <yml-file v-show="show" />
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
  },

  data: () => ({
    show: false
  }),

  mounted() {
    setTimeout(() => {
      this.show = true
    }, 5800)
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
