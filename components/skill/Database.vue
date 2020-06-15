<template>
  <v-card style="background-color: #424242;">
    <v-card-subtitle class="title">Database</v-card-subtitle>
    <v-card-text>
      <span class="mx-10" v-for="(db, i) in dbList" :key="i">
        <div class="my-3" style="display: inline-block;">
          <img
            :src="img(db.name)"
            width="30"
            alt="lang-img"
            style="vertical-align: middle;"
          />
          <span class="db-name ml-2" style="vertical-align: middle;">{{
            db.name
          }}</span>
        </div>
      </span>
    </v-card-text>
  </v-card>
</template>

<script lang="ts">
import Vue from 'vue'
const img_url = 'https://cdn.svgporn.com/logos/'

export default Vue.extend({
  data: () => ({
    dbList: [{ name: 'MySQL' }, { name: 'PostgreSQL' }, { name: 'MongoDB' }]
  }),

  computed: {
    img: function() {
      return function(db: String) {
        db = db == 'C++' ? 'c-plusplus' : db.toLowerCase().replace('.', '')
        return img_url + db + '.svg'
      }
    }
  }
})
</script>

<style scoped>
.db-name {
  font-size: 16px;
  color: #b0bec5;
}

@media screen and (min-width: 630px) {
  .db-name {
    font-size: 20px;
  }
}

@media screen and (min-width: 600px) {
  .db {
    margin-top: 75px;
  }
}

@media screen and (min-width: 1264px) {
  .db {
    margin-top: 50px;
  }
}
</style>
