<template>
  <div class="root">
    <button type="button" @click="isModal = !isModal">Принять</button>
    <Modal v-if="isModal" :title="title"> </Modal>
  </div>
</template>

<script>
import Modal from '@/components/Task4/Modal.vue'
export default {
  name: 'MainVue4',
  components: { Modal },

  data() {
    return {
      title: 'Окно',
      isModal: false,
    }
  },
  computed: {},
  watch: {},
  methods: {},
}
</script>

<style>
button {
  background-color: rgb(168, 210, 254);
  border: none;
  border-radius: 0.5rem;
  width: 5rem;
  height: 2rem;
}
</style>
