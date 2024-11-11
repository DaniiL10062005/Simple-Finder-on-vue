<template>
  <div class="Card">
    <img :src="imgUrl" alt="Sorry" />
    <h3>{{ title }}</h3>
    <p style="margin: 0rem">{{ price }} руб.</p>
    <p style="margin: 0.5rem">{{ count }} шт.</p>
    <button :disabled="count === 0" ref="Choose">Выбрать</button>
  </div>
</template>

<script>
export default {
  props: {
    imgUrl: String,
    title: String,
    price: Number,
    count: Number,
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
h3 {
  margin: 0rem;
}
.Card {
  display: grid;
  grid-template-columns: 1fr;
  width: 15rem;
  height: 20rem;
  align-items: center;
  justify-items: center;
  margin: 0rem;
  background-color: rgb(230, 230, 230);
  border-radius: 1rem;
}
button {
  width: 5rem;
  height: auto;
  background-color: rgb(253, 94, 94);
  color: aliceblue;
  margin: 0.2rem;
  border-radius: 0.5rem;
}
img {
  width: 100%;
  height: 100%;
  border-radius: 0rem 0rem 1rem 1rem;
  object-fit: cover;
}
</style>
