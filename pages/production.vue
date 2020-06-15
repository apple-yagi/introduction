<template>
  <v-container>
    <h1 align="center">Production</h1>
    <v-row justify="center">
      <v-col cols="12" sm="9" md="7" v-for="(production, index) in Productions" :key="index">
        <production-card :production="production" />
      </v-col>
    </v-row>
  </v-container>
</template>

<script lang="ts">
import Vue from 'vue'
import ProductionCard from '@/components/production/ProductionCard.vue'
import Productions from '@/data/productions'

export default Vue.extend({
  name: 'Production',
  components: {
    ProductionCard
  },

  data: () => ({
    Productions
  })
})
</script>