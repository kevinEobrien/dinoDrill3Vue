<template>
  <div id="app">
    <TheHeader/>
    <main>
    <JobDetails :listings="listingData"/>
    <InputForm :text= "applicationText"/>
    </main>
    <TheFooter/>
  </div>
</template>

<script>
import TheHeader from "./components/TheHeader"
import TheFooter from "./components/TheFooter"
import Preview from "./components/Preview"
import JobDetails from "./components/JobDetails"
import InputForm from "./components/InputForm"
export default {
  name: 'App',
  components: {
    TheHeader, TheFooter, Preview, JobDetails, InputForm
  },
  methods:{
    // getText(text){
    //   this.applicationText = text;
    // },
    getListings(){
      fetch(this.apiURL)
      .then(response => response.json())
      .then(response => {
          this.listingData = response
          console.log(this.listingData)
          })
    }
  },
  data(){
     return{
    apiURL: "../static/listing.json",
    listingData: [],
    applicationText: ""
    }
  },
    mounted(){
    this.getListings();
  }
}
</script>

<style>
html{
  margin: 0;
  padding: 0;
}
a {
  color: #C261CC;
  text-decoration: none;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  font-family: sans-serif;
  color: #1B997A;
  margin-top: 60px;
  grid-row: 2/3;
  width: 70%;
  margin: 0 auto;
  padding: 10px;
}
section {
  grid-column: 2/3;
}
.hidden {
  display: none;
}
</style>
