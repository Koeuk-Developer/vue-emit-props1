<template>
  <div class="container">
    <!--  -->
    <AlertComponentVue :post="alertMessages" />
    <CardComponentVue
      v-for="(post, index) in posts"
      :key="index"
      :id="post.id"
      :userId="post.userId"
      :title="post.title"
      :body="post.body"
      @dataPost="handlePost"
    />
  </div>
  <!-- <h2 v-for="(post, index) in posts" :key="index">{{ post.userId }}</h2> -->

</template>

<script>
import AlertComponentVue from "./components/AlertComponent.vue";
import CardComponentVue from "./components/CardComponent.vue";
export default {
  name: "App",
  components: {
    AlertComponentVue,
    CardComponentVue,
  },
  data() {
    return {
      posts: [],
      alertMessages: "",
      title: "",
      comment: "",
      userId: "",
      id: null,
    };
  },
  // computed
  mounted() {
    fetch("https://jsonplaceholder.typicode.com/posts")
      .then((response) => response.json())
      .then((posts) => {
        this.posts = posts;
        // console.log(posts)
      })
      .catch((error) => console.error(error));
  },

  //

  methods: {
    handlePost(post) {
      this.alertMessages = post;
      console.log(this.title, this.comment, this.userId, this.id);
    },
    methods: {
      handlePost(title,userId) {
        this.title = title;
        this.userId = userId;
      },
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
