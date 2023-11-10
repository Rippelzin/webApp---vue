<template>
  <q-page class="flex flex-center">
    <TodoCard :list="list" :teste="teste" />
  </q-page>
</template>

<script>
/* eslint-disable */
import { defineComponent } from "vue";
import axios from "axios";
import TodoCard from "src/components/Todo-Card.vue";

export default defineComponent({
  name: "IndexPage",

  data() {
    return {
      list: [],
      teste: "teste",
    };
  },
  components: {
    TodoCard,
  },
  mounted() {
    this.fetchData();
    console.log("aa");
    console.log(this.list);
  },
  methods: {
    fetchData() {
      axios
        .get("https://jsonplaceholder.typicode.com/todos")
        .then((response) => (this.list = response.data));
    },
  },
});
</script>
