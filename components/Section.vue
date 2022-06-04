<template>
  <section>
    <v-container :fluid="fluid">
      <slot />
    </v-container>
  </section>
</template>

<script>
export default {
  name: 'HomeSection',
  props: {
    fluid: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style lang="sass">
.title
  color: #de9408
  span
    text-tranform: uppercase
    font-weight: bold
    display: block
    padding-bottom: 6px
    text-transform: uppercase

  &:after
    content: ''
    display: block
    height: 2px
    border-bottom: 1px solid #de9408

</style>
