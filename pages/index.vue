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

      <v-row>
        <v-col
          v-for="(service, index) in services"
          :key="index"
          class="service d-flex flex-column text-center align-center justify-start"
          cols="4"
        >
          <v-img class="ma-2" :src="service.image" max-width="64" max-height="64" contain />
          <span class="pa-2">{{ service.title }}</span>
        </v-col>
      </v-row>
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
      {
        title: 'Projetos de SPDA',
        image: require('@/assets/images/services/project.png'),
      },
      {
        title: 'Gerenciamento de risco conforme NBR 5419-2/2015',
        image: require('@/assets/images/services/briefing.png'),
      },
      {
        title: 'Medidas de proteção contra surtos elétricos (MPS)',
        image: require('@/assets/images/services/electric-meter.png'),
      },
      {
        title: 'Sistema de Aterramento residencial, comercial e industrial',
        image: require('@/assets/images/services/symbol.png'),
      },
      {
        title: 'Laudos técnicos e inspeções',
        image: require('@/assets/images/services/report.png'),
      },
      {
        title: 'Testes e medições de resistividade',
        image: require('@/assets/images/services/checklist.png'),
      },
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
