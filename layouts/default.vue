<template>
  <v-app>
    <client-only placeholder="Loading...">
      <!-- <drawer @switchNavi="switchNavi" :items="items" /> -->
      <Header @switchNavi="switchNavi" :items="items" />
      <!-- <down-drawer v-else @switchNavi="switchNavi" :items="items" /> -->
    </client-only>
    <v-main>
      <nuxt />
    </v-main>
    <Footer />
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue'
import Drawer from '@/components/nav/Drawer.vue'
import DownDrawer from '@/components/nav/DownDrawer.vue'
import Header from '@/components/nav/Header.vue'
import Footer from '@/components/nav/Footer.vue'

export default Vue.extend({
  components: {
    Drawer,
    DownDrawer,
    Header,
    Footer
  },

  data: () => ({
    navi: true,
    items: [
      { title: 'Home', icon: 'mdi-home', link: '/' },
      { title: 'Skill', icon: 'mdi-code-tags', link: '/skill' }
    ]
  }),

  methods: {
    switchNavi(val: boolean) {
      this.navi = val
    }
  }
})
</script>
