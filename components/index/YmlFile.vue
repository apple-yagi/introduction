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
      { text: 'version : ' + new Date().getFullYear(), delay: 6300 },
      { text: 'jobs :', delay: 7500 },
      { text: '  -  4th year University Student', delay: 8300 },
      { text: 'live :', delay: 10800 },
      { text: '  -  Fukuoka', delay: 11600 },
      { text: 'favorite lang :', delay: 12700 },
      { text: '  -  JavaScript, Node.js', delay: 14000 }
    ]
  })
})
</script>
