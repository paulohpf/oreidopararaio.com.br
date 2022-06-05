<template>
  <div class="home">
    <Section fluid class="banner">
      <v-img
        :aspect-ratio="16 / 9"
        :src="require('@/assets/images/banner.jpg')"
        :style="{
          maxHeight: `calc(60vh - ${navBarSize}px)`,
        }"
      />
    </Section>
    <Section title="Sobre" class="about content">
      <div class="d-flex justify-center">
        <div class="title py-2">
          <span>Quem somos</span>
        </div>
      </div>

      <p>
        A REI DO PARA-RAIO, sediada em Bauru-SP, é uma empresa especializada no
        ramo de Proteção Contra Descargas Atmosféricas (PDA). Oferecemos
        soluções inteligentes para implantação e adequação dos Sistemas de
        Proteção contra Descargas Atmosféricas (SPDA). Trabalhamos alinhados com
        os padrões das normas técnicas vigentes garantindo segurança e
        eficiência para a sua instalação.
      </p>
    </Section>
    <Section class="services content">
      <div class="d-flex justify-center">
        <div class="title py-2">
          <span>Nossos serviços</span>
        </div>
      </div>

      <ul class="explained">
        <li
          v-for="(service, index) in services"
          :key="index"
          class="service"
          cols="4"
        >
          {{ service.title }}
        </li>
      </ul>
    </Section>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  components: {
    Section: () => import('@/components/Section.vue'),
  },
  data: () => ({
    services: [
      { title: 'Projetos de SPDA' },
      { title: 'Gerenciamento de risco conforme NBR 5419-2/2015;' },
      { title: 'Medidas de proteção contra surtos elétricos (MPS)' },
      { title: 'Sistema de Aterramento residencial, comercial e industrial' },
      { title: 'Laudos técnicos e inspeções' },
      { title: 'Testes e medições de resistividade' },
    ],
  }),
  computed: {
    navBarSize() {
      if (this.$vuetify.breakpoint.mobile) {
        return 64
      }
      return 56
    },
  },
}
</script>

<style lang="sass">
.home
  .banner
    padding: 0 !important
    .container
      padding: 0
</style>
