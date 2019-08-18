<template>
<p>hello</p>
</template>

<script>
import axios from 'axios';
//let url = 'http://www.omdbapi.com/?s=avengers&page=1&type=movie&Content-Type=application/json';
//let API_KEY = 'b6e26482';
export default {
  data() {
    return {
      wholeResponse: [],
      loading: true,
    }
  },
  mounted() {
    axios.get('https://cors-anywhere.herokuapp.com/http://www.omdbapi.com/?apikey=b6e26482&s=avengers&page=1&type=movie&Content-Type=application/json')
    .then(response => {
      console.log("abc");
      console.log(response);
      this.wholeResponse = response.data.Search;
      this.loading = false;
    })
    .catch(error => {
      console.log("def");
      console.log(error);
    })
  },
}
</script>