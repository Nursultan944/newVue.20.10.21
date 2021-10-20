<template>
  <q-card class="my-card">
    <q-card-section class="bg-teal text-white">
      <div class="text-h6">Список постов</div>
      <div class="text-subtitle2">для подробности откройте элемент</div>
    </q-card-section>


  </q-card>
<div class="block">
<div   v-for="(post, ind) in posts"  :key="ind" class="q-pa-md" style="max-width: 350px">




  <Post :post="post"/>

</div>


</div>
</template>

<script>
import Post from "components/Post";
  import axios from 'axios'
  import PostModal from "./PostModal";
    export default {
    name: 'PostList',
    components: {Post},
    data () {
      return {
        posts: []
      }
    },

      methods: {
        click () {
      axios({
            method: 'get',
            url: 'https://jsonplaceholder.typicode.com/posts'
          }).then((result) => {
            this.posts = result.data
          })

        },

        },

      mounted() {
      this.click()

      }


    }
</script>

<style scoped>
.q-pa-md {
  margin-left: 50px;
  font-family: 'Roboto';
}
.block{
  background-color: whitesmoke;

}

</style>
