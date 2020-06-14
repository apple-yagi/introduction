<template>
  <v-footer app absolute dark padless>
    <v-card
      width="100%"
      flat
      tile
      class="grey darken-4 white--text text-center"
    >
      <v-card-text>
        <v-btn
          v-for="item in items"
          :key="item.icon"
          class="mx-4 white--text"
          icon
          :href="item.link"
          target="_blank"
        >
          <v-icon size="24px">{{ item.icon }}</v-icon>
        </v-btn>
      </v-card-text>

      <v-divider />

      <v-card-text class="white--text">
        {{ new Date().getFullYear() }} - <strong>Yagi</strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'Footer',

  data: () => ({
    items: [
      { icon: 'mdi-twitter', link: 'https://twitter.com/2nSTmOTLY2ltbvS' },
      { icon: 'mdi-github', link: 'https://github.com/apple-yagi' },
      { icon: 'mdi-format-float-left', link: 'https://qiita.com/apple-yagi' }
    ]
  })
})
</script>
