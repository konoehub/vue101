<template>
  <div>
     <button @click="prevPage">PREV</button>
     {{ page }}
     {{ currentUser.name }}
     <button @click="nextPage">NEXT</button>
  </div>
</template>

<script>
export default {
  data () {
    return {
      users: [{ name: 'Jeng' }, {name: 'Tee'}, {name: 'Dome'}],
      page: 0
    }
  },
  methods: {
    prevPage () {
      this.page = (--this.page + this.users.length) % this.users.length
    },
    nextPage () {
      this.page = (++this.page + this.users.length) % this.users.length
    }
  },
  computed: {
    currentUser () {
      return this.users[this.page]
    }
  }
}
</script>

<style>
  div {
    color: green;
    font-size: 5em;
  }
</style>
