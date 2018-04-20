<template>
  <div id="app">
    <Header></Header>
    <main>
      <JobDetails :jobData='jobDetails'></JobDetails>
      <InputForm :getText='getText'></InputForm>
      <button id='preview-toggle' @click='previewToggle = !previewToggle'>Show Preview</button>
      <Preview :text='formText' :class='{hidden : previewToggle}'></Preview>
    </main>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import JobDetails from './components/JobDetails.vue'
import Preview from './components/Preview.vue'
import InputForm from './components/InputForm.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'app',
  data () {
    return{
      jobDetails: {},
      formText: '',
      previewToggle: true
    }
  },
  components: {
   Header,
   JobDetails,
   InputForm,
   Preview,
   Footer
  },
  mounted () {
    const URL = '../../listing.json'
    fetch (URL)
      .then(response => response.json())
      .then(response => {
        this.jobDetails = response
      })
  },
  methods: {
    getText(text) {
      this.formText = text;
    }
  }
}
</script>

<style>
htlm {
  margin: 0;
  padding: 0;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  margin: 0 30px 0 30px;
  padding: 0;
  font-family: sans-serif;
  display: grid;
  grid-template-rows: 15% 75% 10%;
  color: #1B997A;
}
main {
  grid-row: 2/3;
  width: 70%;
  margin: 0 auto;
  padding: 10px;
}
small {
  color: black;
  font-size: .5rem;
  margin-left: 10px;
}
a {
  color: #C261CC;
  text-decoration: none;
}
.hidden {
  display: none;
}
</style>
