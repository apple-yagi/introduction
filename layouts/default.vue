<template>
  <v-app>
    <drawer @switchNavi="switchNavi" :items="items" />
    <down-drawer v-if="!navi" :items="items" />
    <v-main>
      <nuxt />
    </v-main>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue'
import Drawer from '@/components/nav/Drawer.vue'
import DownDrawer from '@/components/nav/DownDrawer.vue'

export default Vue.extend({
  components: {
    Drawer,
    DownDrawer
  },

  data: () => ({
    navi: true,
    items: [{ title: 'Home', icon: 'mdi-home', link: '/' }]
  }),

  methods: {
    switchNavi(val: boolean) {
      this.navi = val
    }
  }
})
</script>