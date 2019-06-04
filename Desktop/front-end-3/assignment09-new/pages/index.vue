<template>
  <section class="container bg-white">
    <!-- data display dashboard -->
    <p>{{dashboard}}</p>
    <!-- event button -->
    <button v-on:click="clickToDisplay">Display</button>
  </section>
</template>

<script>
  import axios from 'axios'
  export default {
    data() {
      return {
         dashboard: "Hello, Click the button to get the weather dashboard"
       }
     },
     created: function() {
       //fetching data from api with api key as a parameter
       axios.get("http://api.apixu.com/v1/forecast.json?key=4fbf8f5b5bd247fd981103359190406&q=Seattle")
       .then(response => {
         // JSON responses are automatically parsed.
         this.posts = response.data
         console.log(this.posts);
       })
       .catch(e => {
         this.errors.push(e)
       })
       .finally(() => this.loading =true)
     },
     methods: {
       clickToDisplay: function() {
         //assign data to dashboard
         this.dashboard = this.posts.location;
       }
     }
   }
</script>

<style>
.container {
  margin: 0 auto;
  /* disable flexbox */
  /* min-height: 30vh; */
  /* display: flex;
  justify-content: center;
  align-items: center;
  text-align: center; */
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
