<template>
  <v-navigation-drawer v-model="navi" width="180px" app fixed absolute>
    <v-list dense nav>
      <v-list-item-avatar>
        <v-icon>mdi-home</v-icon>
      </v-list-item-avatar>

      <v-divider />

      <v-list-item v-for="item in items" :key="item.title" link>
        <v-list-item-icon>
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-item-icon>

        <v-list-item-content>
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'Drawer',

  props: {
    items: {
      type: Array,
      required: true
    }
  },

  data: () => ({
    navi: false
  }),

  mounted() {
    this.navi = window.innerWidth > 1024 ? true : false
  },

  watch: {
    navi(val: boolean) {
      this.$emit('switchNavi', this.navi)
    }
  }
})
</script>