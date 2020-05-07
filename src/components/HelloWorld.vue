<template>
  <div>

<ul v-for="(item, index) in posts" :key="index">
  <li> {{ item.Title }} </li>
</ul>


  </div>
</template>

<script>

import axios from 'axios'

export default {
  name: 'HelloWorld',

  mounted(){
    console.log(this.posts)
  },

  data(){
    return {
        posts: []
    }
  },

  created() {
       axios.get('http://www.omdbapi.com/?i=tt3896198&apikey=7bb03cab&fbclid=IwAR0yWEIC2blJ3nFnkB_HflB_eq6ZZF9C23uLChtRamn36kcn4lmtNaDSGdU')
       .then(response => this.posts = response.data);
   },

}
</script>
