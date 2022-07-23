<template>
  <div class="app">
    <p> {{ name }} - {{ age }}</p>
    <button @click="changeName('Akin')">
      Change name
    </button>
    <button @click="changeAge('32')">
      Change name
    </button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'App',
  components: {},

  data() {
    return {
      name: 'Link',
      age: 25 as number | string // This way we can provide two types for the age variable within the data block
    }
  },

  methods: {
    changeName(name: string) {
      this.name = name;
    },

    changeAge(age: number | string) {
      this.age = age;
    }
  }
});
</script>

<style>

</style>
