<template>
  <div class="m-auto">
    <h1 class="text-2xl text-center">SuperHeroes {{listCount}}</h1>
    <ul>
      <li class="flex justify-between" v-for="(hero, index) in dcHeros" :key="hero.name">
        <div>
          {{hero.name}}
        </div>
        <button v-on:click="remove(index)">x</button>
      </li>
    </ul>
    <form class="mt-10" @submit.prevent="addHero">
      <input class="border rounded" v-model.number="newHero" placeholder="Type Smth Here"/>
      <button class="border rounded bg-gradient-to-t from-red-700 to-pink-500 text-white" type="submit" >Add Item</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newHero:" ",
      dcHeros:
          [
            {name: "SuperGirl"},
            {name: "Flash"},
            {name: "Batman"},
            {name: "Arrow"},
            {name: "SuperMan"},
          ],
    }
  },
  computed: {
    listCount() {
      return this.dcHeros.length;
    },
  },
  methods: {
    addHero() {
      if(this.newHero !== '') {
        this.dcHeros.push({name: this.newHero});
        this.newHero = "";
      }
    },
    remove(index){
      this.dcHeros = this.dcHeros.filter((hero, i) => i !== index);
    },
  },
  // eslint-disable-next-line vue/multi-word-component-names
  name: "List"
}

</script>

<style scoped>

</style>