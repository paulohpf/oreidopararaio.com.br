<template>
  <div class="contact-form d-flex justify-center align-center flex-column text-center">
    <span class="description">Solicite um orçamento</span>
    <form action="">
      <v-text-field label="Nome" name="name" />
      <v-text-field label="E-mail" name="email" />
      <v-text-field label="Telefone" name="phone" />
      <v-textarea label="Mensagem" name="message" />
      <v-btn class="white--text" type="submit" color="#de9408">Enviar</v-btn>
    </form>
  </div>
</template>

<script>
export default {
  name: 'ContactForm',
}
</script>

<style lang="sass" scoped>
.contact-form
  .description
    // font-weight: bold
    color: #de9408

  form
    width: 360px
</style>
