<template>
  <v-app>
    <AppHeader />
    <v-main>
      <v-container max-width="75%">
        <Nuxt />
      </v-container>
    </v-main>
    <AppFooter />
  </v-app>
</template>
<script>
import AppFooter from '@/components/AppFooter.vue'
import AppHeader from '@/components/AppHeader.vue'

export default {
  components: {
    AppHeader,
    AppFooter,
  },
}
</script>
