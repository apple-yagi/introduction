<template>
  <v-card class="mx-auto">
    <v-img :src="production.img" alt="production_img"></v-img>

    <v-card-title>{{ production.title }}</v-card-title>
    <v-card-subtitle>Created at {{ production.date }}</v-card-subtitle>

    <v-card-text>
      <p v-if="production.description">
        <span class="subtitle-1 font-weight-bold">Description</span>
        <br />
        &ensp;{{ production.description }}
      </p>
      <p>
        <span class="font-weight-bold">使用した技術</span>
        <br />
        &ensp;
        {{
        production.tec
        }}
      </p>

      <div v-if="production.url">
        <v-layout justify-end>
          <v-btn :href="production.url" target="_blank" large text>
            <v-icon class="mr-1">mdi-earth</v-icon>Webページへ
          </v-btn>
          <v-btn :href="production.github" target="_blank" large text>
            <v-icon class="mr-1">mdi-github</v-icon>Github
          </v-btn>
        </v-layout>
      </div>

      <div v-if="production.article" class="font-weight-bold">
        <v-layout justify-end>
          <v-btn :href="production.article" target="_blank" large text>
            <v-icon class="mr-1">mdi-format-float-right</v-icon>Qiita記事
          </v-btn>
          <v-btn :href="production.github" target="_blank" large text>
            <v-icon class="mr-1">mdi-github</v-icon>Github
          </v-btn>
        </v-layout>
      </div>
    </v-card-text>
  </v-card>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'ProductionCard',

  props: {
    production: {
      type: Object,
      required: true
    }
  }
})
</script>