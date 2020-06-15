<template>
  <v-app>
    <Header :items="items" />
    <v-main>
      <nuxt />
    </v-main>
    <Footer />
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue'
import Header from '@/components/nav/Header.vue'
import Footer from '@/components/nav/Footer.vue'

export default Vue.extend({
  components: {
    Header,
    Footer
  },

  data: () => ({
    items: [
      { title: 'Home', icon: 'mdi-home', link: '/' },
      { title: 'Skill', icon: 'mdi-code-tags', link: '/skill' },
      { title: 'Production', icon: 'mdi-responsive', link: '/production' }
    ]
  })
})
</script>
