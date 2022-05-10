<template>
  <v-app>
    <v-app-bar id="navbar" color="#fff" fixed app>
      <div class="header">
        <LogoHeader />
      </div>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <Footer />
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  components: {
    Footer: () => import('@/components/Footer.vue'),
    LogoHeader: () => import('@/components/Logo/Header.vue'),
  },
  data: () => ({}),
}
</script>

<style lang="sass">
.header
  height: 100%
  overflow: hidden
</style>
