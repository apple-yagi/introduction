<template>
  <v-app-bar app fixed height="50">
    <v-container>
      <v-layout justify-space-around>
        <v-btn
          v-for="(item, index) in items"
          :key="index"
          color="white"
          nuxt
          :to="item.link"
          rounded
          class="my-2"
          text
        >
          <v-icon>{{ item.icon }}</v-icon>
          <span class="hidden-sm-and-down ml-2">{{ item.title }}</span>
        </v-btn>
      </v-layout>
    </v-container>
  </v-app-bar>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'Header',
  props: {
    items: {
      type: Array,
      required: true
    }
  },

  data: () => ({
    width: 0
  }),

  methods: {
    handleResize() {
      this.width = window.innerWidth
      this.$emit('switchNavi', this.width > 1024 ? true : false)
    }
  },

  mounted() {
    window.addEventListener('resize', this.handleResize)
    this.handleResize()
  },

  beforeDestroy() {
    window.removeEventListener('resize', this.handleResize)
  }
})
</script>
