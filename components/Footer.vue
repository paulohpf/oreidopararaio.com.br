<template>
  <v-footer color="#df9405" :absolute="true" app>
    <v-row class="footer ma-0" justify="space-between">
      <v-col
        :cols="isMobile ? 12 : 4"
        class="contact d-flex justify-center align-center"
      >
        <div class="d-flex flex-column">
          <div class="title">
            <span>Contato</span>
          </div>

          <div class="contact-item d-flex flex-column">
            <span>Telefone</span>
            <a href="tel:+5514998964464">(14) 99896-4464</a>
          </div>
          <div class="contact-item d-flex flex-column">
            <span>E-mail</span>
            <a href="mailto:contato@oreidopararaio.com.br"
              >contato@oreidopararaio.com.br</a
            >
          </div>
        </div>
      </v-col>

      <v-col
        :cols="isMobile ? 12 : 4"
        class="copyright d-flex justify-center align-center"
      >
        <span>O Rei do Pararaio &copy; {{ new Date().getFullYear() }}</span>
      </v-col>

      <v-col
        :cols="isMobile ? 12 : 4"
        class="social d-flex justify-center align-center"
      >
        <a
          class="social-link"
          href="https://www.facebook.com/oreidopararaio"
          target="_blank"
          rel="noopener noreferrer"
        >
          <Facebook color="#fff" />
        </a>
        <a
          class="social-link"
          href="https://www.instagram.com/oreidopararaio/"
          target="_blank"
          rel="noopener noreferrer"
        >
          <Instagram color="#fff" />
        </a>
      </v-col>
    </v-row>
  </v-footer>
</template>

<script>
// import Logo from '@/components/LogoFooter.vue'
import Facebook from '@/assets/images/footer/social/Facebook.vue'
import Instagram from '@/assets/images/footer/social/Instagram.vue'
// import YouTube from '@/assets/images/footer/social/YouTube.vue'

export default {
  name: 'DefaultFooter',
  components: {
    // Logo,
    Facebook,
    Instagram,
    // YouTube,
  },
  computed: {
    isMobile() {
      return this.$vuetify.breakpoint.mobile
    },
  },
}
</script>

<style lang="sass" scoped>
.footer
  font-family: 'Open Sans', sans-serif
  display: flex
  justify-content: space-around
  padding: 18px 0
  color: #fff

  .social
    .social-link:not(:last-child)
      padding-right: 16px

  .copyright
    font-size: 12px

  //Area de contato
  .contact
    .title
      font-weight: bold

      span
        display: block
        padding-bottom: 6px
        text-transform: uppercase

      &:after
          content: ''
          display: block
          width: 100%
          height: 1px
          border-bottom: 1px solid #fff

    //Item de contato
    .contact-item
      margin: 8px
      color: #fff

      span
        font-size: 0.8em
        margin: 8px 0
        font-weight: bold
        text-transform: uppercase

      a
        color: #fff
        text-decoration: none

</style>


