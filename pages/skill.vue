<template>
  <v-container>
    <h1 class="mt-5" align="center">Skills</h1>
    <v-row>
      <v-layout justify-center>
        <v-col align="center" cols="12" sm="10" lg="8">
          <pro-lang />
        </v-col>
      </v-layout>
      <v-layout justify-center>
        <v-col align="center" cols="12" sm="10" lg="8">
          <framework class="mt-10" />
        </v-col>
      </v-layout>
      <v-layout justify-center>
        <v-col align="center" cols="12" sm="10" lg="8">
          <database class="mt-10" />
        </v-col>
      </v-layout>
      <v-layout justify-center>
        <v-col align="center" cols="12" sm="10" lg="8">
          <AWS class="mt-10" />
        </v-col>
      </v-layout>
      <v-layout justify-center>
        <v-col align="center" cols="12" sm="10" lg="8">
          <other class="my-10" />
        </v-col>
      </v-layout>
    </v-row>
  </v-container>
</template>

<script lang="ts">
import Vue from 'vue'
import ProLang from '@/components/skill/ProLang.vue'
import Framework from '@/components/skill/FrameWork.vue'
import Database from '@/components/skill/Database.vue'
import AWS from '@/components/skill/AWS.vue'
import Other from '@/components/skill/Other.vue'

export default Vue.extend({
  components: {
    ProLang,
    Framework,
    Database,
    AWS,
    Other
  }
})
</script>
