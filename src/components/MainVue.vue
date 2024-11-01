<template>
  <div class="root">
    <h1>Finder</h1>
    <input
      type="text"
      :value="name"
      v-on:input="findChanges($event.target.value)"
    />
    <p>Всего имен: {{ countOfPerson }}, совпадений: {{ countOfSovpad }}</p>

    <p v-for="user in search" :key="user.id">
      {{ `${user.us}` }}
    </p>
  </div>
</template>

<script>
export default {
  data() {
    const users = [
      {
        us: 'Артем Иванов Артурович',
      },
      {
        us: 'Иван Прещепкин Владимирович',
      },
      {
        us: 'Влад Карпенко Какой-то',
      },
      {
        us: 'Станисла Вечерковский Нормис',
      },
      {
        us: 'Ярослав Кожемякин Денисович',
      },
      {
        us: 'Влад Карпенко Какой-то',
      },
    ]
    return {
      name: '',
      countOfPerson: users.length,
      countOfSovpad: users.length,
      users,
    }
  },
  computed: {
    search() {
      const inp = this.name.toLowerCase()
      const ans = []

      this.users.forEach(element => {
        if (element.us.toLowerCase().includes(inp)) {
          ans.push(element)
        }
      })
      return ans
    },
  },
  watch: {
    name(newName) {
      this.countOfSovpad = this.search.length
    },
  },
  methods: {
    findChanges(value) {
      this.name = value
    },
  },
}
</script>
