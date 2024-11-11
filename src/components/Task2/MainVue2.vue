<template>
  <div class="root">
    <h1>Ассемблер(</h1>

    <img
      class="code"
      src="@/assets/Capture001.png"
      v-if="visibility"
      :class="Filters"
      :style="imgSize"
    />
    <p v-else>Здесь находится ужас.</p>

    <button v-on:click="changeWordInButton()">
      {{ textInButtonShow }}
    </button>
    <button
      :class="Filters.sepia ? 'active' : ''"
      type="button"
      @click="Filters.sepia = !Filters.sepia"
    >
      Сепия
    </button>
    <button
      :class="Filters.border ? 'active' : ''"
      type="button"
      @click="Filters.border = !Filters.border"
    >
      Обводка
    </button>
    <button
      :class="Filters.shadow ? 'active' : ''"
      type="button"
      @click="Filters.shadow = !Filters.shadow"
    >
      Тени
    </button>
    <p>Ширина: {{ width }}</p>
    <input
      type="range"
      :max="maxWidth"
      :min="0"
      :value="width"
      v-on:input="width = $event.target.value"
    />
    <p>Высота: {{ height }}</p>
    <input
      type="range"
      :max="maxHeight"
      :min="0"
      :value="height"
      v-on:input="height = $event.target.value"
    />
    <p>Угол наклона: {{ rotate }}</p>
    <input
      type="range"
      :max="maxRotate"
      :min="0"
      :value="rotate"
      v-on:input="rotate = $event.target.value"
    />
  </div>
</template>

<script>
export default {
  name: 'MainVue2',
  data() {
    return {
      visibility: true,
      textInButtonShow: 'Скрыть',

      maxWidth: 40,
      maxHeight: 40,

      width: 40,
      height: 40,

      rotate: 0,
      maxRotate: 360,

      Filters: {
        sepia: false,
        border: false,
        shadow: false,
      },
    }
  },
  methods: {
    changeWordInButton() {
      this.textInButtonShow = this.textInButtonShow ? 'Показать' : 'Скрыть'
      this.visibility = !this.visibility
    },
  },
  computed: {
    imgSize() {
      return {
        width: `${this.width}rem`,
        height: `${this.height}rem`,
        rotate: `${this.rotate}deg`,
      }
    },
  },
}
</script>

<style>
p {
  font-size: 20px;
}
.active {
  background-color: gray;
}
.code {
  width: 40rem;
  height: 40rem;
}
.code.sepia {
  filter: sepia(0.5);
}
.code.border {
  border-radius: 1rem;
}
.code.shadow {
  filter: drop-shadow(5px 5px 5px rgba(0, 0, 0, 0.5));
}
</style>
