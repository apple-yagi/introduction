<template>
  <v-card style="background-color: #424242;">
    <v-row class="reverse">
      <v-col align="center" cols="12" sm="4">
        <v-img class="fullscreen" src="img/fullscreen.png" alt="fullscreen" />
      </v-col>

      <v-col align="center" cols="12" sm="8">
        <v-card-subtitle class="title">Framework</v-card-subtitle>
        <v-card-text>
          <span class="mx-10" v-for="(framework, i) in frameworks" :key="i">
            <div class="my-3" style="display: inline-block;">
              <img
                :src="img(framework.name)"
                width="30"
                alt="framework-img"
                style="vertical-align: middle;"
              />
              <span class="fw-name ml-2" style="vertical-align: middle;">{{ framework.name }}</span>
              <div class="subtitle mt-2">学習期間：{{ framework.experience }}</div>
            </div>
          </span>
        </v-card-text>
      </v-col>
    </v-row>
  </v-card>
</template>

<script lang="ts">
import Vue from 'vue'
const img_url = 'https://cdn.svgporn.com/logos/'

export default Vue.extend({
  data: () => ({
    frameworks: [
      { name: 'Ruby on Rails', experience: '1年' },
      { name: 'Django', experience: '1ヶ月' },
      { name: 'Vue', experience: '6ヶ月' },
      { name: 'Nuxt', experience: '2ヶ月' },
      { name: 'Express', experience: '3ヶ月' }
    ]
  }),

  computed: {
    img: function() {
      return function(lang: String) {
        lang =
          lang == 'Ruby on Rails'
            ? 'rails'
            : lang.toLowerCase().replace('.', '')
        return img_url + lang + '.svg'
      }
    }
  }
})
</script>

<style scoped>
@media screen and (max-width: 600px) {
  .reverse {
    flex-flow: column-reverse;
  }
}

.fw-name {
  font-size: 16px;
  color: #b0bec5;
}

@media screen and (min-width: 630px) {
  .fw-name {
    font-size: 20px;
  }
}

.fullscreen {
  animation: 10s infinite alternate forwards running scale;
}

@media screen and (min-width: 600px) {
  .fullscreen {
    margin-top: 100px;
  }
}

@media screen and (min-width: 1264px) {
  .fullscreen {
    margin-top: 75px;
  }
}

@keyframes scale {
  from {
    width: 50px;
  }

  to {
    width: 150px;
  }
}
</style>