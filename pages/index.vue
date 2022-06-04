<template>
  <div class="home">
    <Section fluid class="pa-0">
      <v-img
        :aspect-ratio="16 / 9"
        :src="require('@/assets/images/banner.jpg')"
        :style="{
          maxHeight: `calc(50vh - ${navBarSize}px)`,
        }"
      />
    </Section>
    <Section title="Sobre">
      <div class="content">
        <div class="d-flex justify-center">
          <div class="title py-2">
            <span>Quem somos</span>
          </div>
        </div>

        <p>
          A REI DO PARA-RAIO, sediada em Bauru-SP, é uma empresa especializada
          no ramo de Proteção Contra Descargas Atmosféricas (PDA). Oferecemos
          soluções inteligentes para implantação e adequação dos Sistemas de
          Proteção contra Descargas Atmosféricas (SPDA). Trabalhamos alinhados
          com os padrões das normas técnicas vigentes garantindo segurança e
          eficiência para a sua instalação.
        </p>

        <p>
          Nossos serviços: Projetos de SPDA; Gerenciamento de risco conforme NBR
          5419-2/2015; Medidas de proteção contra surtos elétricos (MPS);
          Sistema de Aterramento residencial, comercial e industrial; Laudos
          técnicos e inspeções; Testes e medições de resistividade.
        </p>
      </div>
    </Section>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  components: {
    Section: () => import('@/components/Section.vue'),
  },
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
