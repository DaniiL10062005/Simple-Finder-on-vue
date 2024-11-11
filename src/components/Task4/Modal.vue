<template>
  <div class="Modal">
    <h4>{{ title }}</h4>
  </div>
</template>

<script>
export default {
  name: 'Modal',
  props: {
    title: String,
  },

  data() {
    return {}
  },
  computed: {},
  watch: {},
  methods: {},
}
</script>
<style>
div {
  position: absolute;
  background-color: antiquewhite;
  border-radius: 0.5rem;
}
</style>
