<template>
  <v-row>
    <v-layout justify-center>
      <v-col cols="12" sm="10" lg="8">
        <v-sheet>
          <span class="body-1" style="background-color: #555;">profile.yml</span>
          <v-container>
            <client-only>
              <div v-for="(code, i) in codes" class="my-1" :key="i">
                <vue-typer :text="code.text" :repeat="0" :pre-type-delay="code.delay"></vue-typer>
              </div>
            </client-only>
          </v-container>
        </v-sheet>
      </v-col>
    </v-layout>
  </v-row>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'YmlFile',

  data: () => ({
    codes: [
      { text: 'version : ' + new Date().getFullYear(), delay: 5800 },
      { text: 'jobs :', delay: 7000 },
      { text: '  -  4th year University Student', delay: 7800 },
      { text: 'live :', delay: 10300 },
      { text: '  -  Fukuoka', delay: 11100 },
      { text: 'favorite lang :', delay: 12200 },
      { text: '  -  JavaScript, Node.js', delay: 13500 }
    ]
  })
})
</script>
