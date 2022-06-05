<template>
  <v-footer color="#DDDDDD" class="pa-0 ma-0" :absolute="true" app>
    <div class="footer d-flex flex-column">
      <div class="d-flex justify-center">
        <div class="title py-2">
          <span>Contato</span>
        </div>
      </div>
      <v-row class="footer pa-4" justify="space-between">
        <v-col :cols="isMobile ? 12 : 6" class="justify-center align-center">
          <ContactForm />
        </v-col>
        <v-col :cols="isMobile ? 12 : 6" class="contact d-flex justify-center">
          <div class="d-flex flex-column">
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
            <div class="contact-item social d-flex flex-column">
              <span>Social</span>
              <div class="d-flex flex-row">
                <a
                  class="social-link"
                  href="https://www.facebook.com/oreidopararaio"
                  target="_blank"
                  rel="noopener noreferrer"
                >
                  <Facebook color="rgba(0,0,0,.87)" />
                </a>
                <a
                  class="social-link"
                  href="https://www.instagram.com/oreidopararaio/"
                  target="_blank"
                  rel="noopener noreferrer"
                >
                  <Instagram color="rgba(0,0,0,.87)" />
                </a>
                <a
                  class="social-link"
                  :href="whatsAppLink"
                  target="_blank"
                  rel="noopener noreferrer"
                >
                  <WhatsApp color="rgba(0,0,0,.87)" />
                </a>
              </div>
            </div>
          </div>
        </v-col>
      </v-row>
      <div
        class="copyright d-flex justify-center align-center pa-4 white--text"
      >
        <span>O Rei do Pararaio &copy; {{ new Date().getFullYear() }}</span>
      </div>
    </div>
  </v-footer>
</template>

<script>
export default {
  name: 'DefaultFooter',
  components: {
    ContactForm: () => import('@/components/ContactForm.vue'),
    Facebook: () => import('@/assets/images/footer/social/Facebook.vue'),
    Instagram: () => import('@/assets/images/footer/social/Instagram.vue'),
    WhatsApp: () => import('@/assets/images/footer/social/WhatsApp.vue'),
  },
  data: () => ({
    whatsapp: {
      phone: '5514998964464',
      message: 'Olá, encontrei seu site e gostaria de tirar algumas dúvidas!',
    },
  }),
  computed: {
    isMobile() {
      return this.$vuetify.breakpoint.mobile
    },
    whatsAppLink() {
      return `https://api.whatsapp.com/send?phone=${this.whatsapp.phone}&text=${this.whatsapp.message}`
    },
  },
}
</script>

<style lang="sass" scoped>
.footer
  width: 100%
  display: flex
  justify-content: space-around
  font-family: 'Open Sans', sans-serif
  // color: rgba(0,0,0,.87)

  .title
    color: #de9408
    span
      font-weight: bold
      display: block
      padding-bottom: 6px
      text-transform: uppercase

    &:after
      content: ''
      display: block
      // width: 100%
      height: 2px
      border-bottom: 1px solid #de9408

  .copyright
    background-color: #de9408
    font-size: 12px
    text-transform: uppercase

  //Area de contato
  .contact
    .social
      .social-link:not(:last-child)
        padding-right: 16px

    //Item de contato
    .contact-item
      margin: 8px
      color: #de9408

      span
        font-size: 0.8em
        margin: 8px 0
        font-weight: bold
        text-transform: uppercase

      a
        color: rgba(0,0,0,.87)
        text-decoration: none
</style>


