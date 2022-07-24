<template>
  <div class="app">
    <header>
      <div class="title">
        <img src="./assets/heart.svg" alt="JobsStats">
        <h1>Jobs Stats</h1>
      </div>
      <div class="order">
        <button @click="handleSorting('title')">Order by title</button>
        <button @click="handleSorting('salary')">Order by salary</button>
        <button @click="handleSorting('location')">Order by location</button>
      </div>
    </header>
    <JobsList :jobs="jobs" :order="order" />
  </div>
</template>

<script lang="ts">
import Job from "@/types/Job";
import OrderTerm from "@/types/OrderTerm";
import JobsList from "@/components/JobsList.vue";
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'App',
  components: {
    JobsList,
  },

  setup() {
    const jobs = ref<Job[]>([
      {
        title: 'mason',
        location: 'london ranch',
        salary: 30000,
        id: '1'
      },
      {
        title: 'quarryman',
        location: 'death mountain',
        salary: 40000,
        id: '2'
      },
      {
        title: 'musician',
        location: 'the woods',
        salary: 35000,
        id: '3'
      },
      {
        title: 'fisherman',
        location: 'lake hylia',
        salary: 21000,
        id: '4'
      },
      {
        title: 'prison guard',
        location: 'gerudo valley',
        salary: 32000,
        id: '5'
      }
    ])

    const order = ref<OrderTerm>('title');

    const handleSorting = (term: OrderTerm) => {
      order.value = term;
    }

    return {
      jobs,
      handleSorting,
      order
    }
  },
});
</script>

<style>
  header {
    text-align: center;
  }

  header .order {
    margin-top: 20px;
  }

  button {
    margin: 0 10px;
    color: #1195c9;
    border: 3px solid #1195c9;
    background: #d5f0ff;
    padding: 0.5rem 1rem;
    border-radius: 4px;
    cursor: pointer;
    font-weight: bold;
  }

  header .title {
    display: flex;
    justify-content: center;
  }

  header img {
    width: 60px;
    margin-right: 20px;
  }

  header h1 {
    font-size: 3em;
  }

</style>
