<template>
  <v-app>
    <HeaderComponent />
    <v-container max-width="75%">
      <v-main>
        <Nuxt />
      </v-main>
    </v-container>
    <FooterComponent />
  </v-app>
</template>
<script>
import FooterComponent from '~/components/footerComponent.vue'
import HeaderComponent from '~/components/headerComponent.vue'

export default {
  components: {
    HeaderComponent,
    FooterComponent,
  },
}
</script>
