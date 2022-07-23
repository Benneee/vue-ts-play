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

  setup() {
    // const state = reactive({
    //   name: 'Link',
    //   age: 25 as string | number
    // })

    // const name = ref('Link');
    // const age = ref<number | string>(25) // This uses generic to infer the type

    return {
      // ...toRefs(state)
      // name,
      // age
    }
  },

  // data() {
  //   return {
  //     name: 'Link',
  //     age: 25 as number | string // This way we can provide two types for the age variable within the data block
  //   }
  // },

  // methods: {
  //   changeName(name: string) {
  //     this.name = name;
  //   },

  //   changeAge(age: number | string) {
  //     this.age = age;
  //   }
  // },
});
</script>

<style>

</style>
