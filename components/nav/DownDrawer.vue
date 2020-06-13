<template>
  <div>
    <v-btn class="toggle-btn" @click.stop="drawer = !drawer" fab dark :color="btnColor">
      <v-icon dark>mdi-format-list-bulleted-square</v-icon>
    </v-btn>
    <v-navigation-drawer v-model="drawer" :height="drawerHeight" fixed bottom temporary>
      <v-list dense>
        <v-list-item v-for="(item, i) in items" :key="i" :to="item.link" nuxt>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </div>
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
    drawer: false,
    btnColor: '#26A69A',
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
  },

  computed: {
    drawerHeight(): number {
      return this.items.length * 50
    }
  }
})
</script>

<style scoped>
.toggle-btn {
  z-index: 1;
  position: fixed;
  bottom: 50px;
  right: 50px;
}
</style>