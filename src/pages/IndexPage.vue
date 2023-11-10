<template>
  <q-page class="flex flex-center">
    <!--<TodoCard :list="list" :teste="teste" />-->
    <PostCard :list="listPosts" />
  </q-page>
</template>

<script>
/* eslint-disable */
import { defineComponent } from "vue";
import axios from "axios";
import TodoCard from "src/components/Todo-Card.vue";
import PostCard from "src/components/Post-Card.vue";

export default defineComponent({
  name: "IndexPage",

  data() {
    return {
      list: [],
      listPosts: [],
    };
  },
  components: {
    TodoCard,
    PostCard,
  },
  mounted() {
    this.fetchDataTodos();
    this.fetchDataPosts();
    console.log("aa");
    console.log(this.list);
  },
  methods: {
    fetchDataTodos() {
      axios
        .get("https://jsonplaceholder.typicode.com/todos")
        .then((response) => (this.list = response.data));
    },

    fetchDataPosts() {
      axios
        .get("https://jsonplaceholder.typicode.com/posts")
        .then((response) => (this.listPosts = response.data));
    },
  },
});
</script>
