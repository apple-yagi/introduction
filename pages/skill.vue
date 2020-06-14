<template>
  <v-container>
    <h1 class="mt-5" align="center">Skills</h1>
    <pro-lang />
    <framework class="mt-10" />
    <database class="mt-10" />
    <AWS class="mt-10" />
  </v-container>
</template>

<script lang="ts">
import Vue from 'vue'
import ProLang from '@/components/skill/ProLang.vue'
import Framework from '@/components/skill/FrameWork.vue'
import Database from '@/components/skill/Database.vue'
import AWS from '@/components/skill/AWS.vue'

export default Vue.extend({
  components: {
    ProLang,
    Framework,
    Database,
    AWS
  }
})
</script>
