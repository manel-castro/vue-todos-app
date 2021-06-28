<template>
  <button @click="onClick()" :style="{ background: color}" class="btn">
    {{text}}
  </button>
</template>

<script>
  export default {
    name: 'Button',
    props: {
      text: String,
      color: String,
      action: Function,
    },
    methods: {
      onClick() {
        this.$emit('btn-click') //reusable
      }
    }
  }
</script>