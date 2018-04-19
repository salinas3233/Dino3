<template>
  <div id="app">
    <Header></Header>
    <JobDetails :listings='listings'></JobDetails>
    <InputForm></InputForm>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import JobDetails from './components/JobDetails.vue'
// import Preview from './components/Preview.vue'
import InputForm from './components/InputForm.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'app',
  data () {
    return{
      listings: []
    }
  },
  components: {
   Header,
   JobDetails,
   InputForm,
   Footer
  },
  mounted () {
    const URL = './listings.json'
    fetch (URL)
      .then(response => response.json())
      .then(response => {
        this.listings = response
      })
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
