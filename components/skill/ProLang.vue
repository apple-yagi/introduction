<template>
  <v-card style="background-color: #424242;">
    <v-row>
      <v-col align="center" cols="12" sm="8">
        <v-card-subtitle class="title">Programming Language</v-card-subtitle>
        <v-card-text>
          <span class="mx-10" v-for="(lang, i) in langList" :key="i">
            <div class="my-3" style="display: inline-block;">
              <img :src="img(lang.name)" width="30" alt="lang-img" style="vertical-align: middle;" />
              <span class="lang-name ml-2" style="vertical-align: middle;">{{ lang.name }}</span>
              <div class="subtitle mt-2">学習期間：{{ lang.experience }}</div>
            </div>
          </span>
        </v-card-text>
      </v-col>

      <v-col align="center" cols="12" sm="4">
        <v-img class="gear" src="img/gear.png" alt="gear" width="100" />
      </v-col>
    </v-row>
  </v-card>
</template>

<script lang="ts">
import Vue from 'vue'
const img_url = 'https://cdn.svgporn.com/logos/'

export default Vue.extend({
  data: () => ({
    langList: [
      { name: 'C++', experience: '1年' },
      { name: 'Java', experience: '1年' },
      { name: 'Python', experience: '3ヶ月' },
      { name: 'Ruby', experience: '1ヶ月' },
      { name: 'JavaScript', experience: '6ヶ月' },
      { name: 'Node.js', experience: '3ヶ月' },
      { name: 'TypeScript', experience: '1ヶ月' }
    ]
  }),

  computed: {
    img: function() {
      return function(lang: String) {
        lang =
          lang == 'C++' ? 'c-plusplus' : lang.toLowerCase().replace('.', '')
        return img_url + lang + '.svg'
      }
    }
  }
})
</script>

<style scoped>
.lang-name {
  font-size: 16px;
  color: #b0bec5;
}

@media screen and (min-width: 630px) {
  .lang-name {
    font-size: 20px;
  }
}

.gear {
  animation: 10s infinite alternate forwards running rotation;
}

@media screen and (min-width: 600px) {
  .gear {
    margin-top: 100px;
  }
}

@media screen and (min-width: 1264px) {
  .gear {
    margin-top: 75px;
  }
}

@keyframes rotation {
  from {
    transform: rotate(0);
  }

  to {
    transform: rotate(360deg);
  }
}
</style>