<template>
  <v-card style="background-color: #424242;">
    <v-row class="reverse">
      <v-col align="center" cols="12" sm="4">
        <v-img class="aws" src="img/aws.jpeg" alt="aws" width="125" />
      </v-col>

      <v-col align="center" cols="12" sm="8">
        <v-card-subtitle class="title">Amazon Web Service</v-card-subtitle>
        <v-card-text>
          <span class="mx-10" v-for="(service, i) in aws" :key="i">
            <div class="my-3" style="display: inline-block;">
              <img :src="img(service)" width="30" alt="aws-img" style="vertical-align: middle;" />
              <span class="aws-name ml-2" style="vertical-align: middle;">{{ service }}</span>
            </div>
          </span>
        </v-card-text>
      </v-col>
    </v-row>
  </v-card>
</template>

<script lang="ts">
import Vue from 'vue'
const img_url = 'img/aws/'

export default Vue.extend({
  data: () => ({
    aws: ['EC2', 'RDS', 'S3', 'Lambda', 'ECS', 'Fargate', 'API-Gateway']
  }),

  computed: {
    img: function() {
      return function(lang: String) {
        lang = lang.toLowerCase().replace('.', '')
        return img_url + lang + '.png'
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

.aws-name {
  font-size: 16px;
  color: #b0bec5;
}

@media screen and (min-width: 630px) {
  .aws-name {
    font-size: 20px;
  }
}

@media screen and (min-width: 600px) {
  .aws {
    margin-top: 100px;
  }
}

@media screen and (min-width: 1264px) {
  .aws {
    margin-top: 50px;
  }
}
</style>