<template>
  <div class="container">
    <!-- #3 must use the component-->
    <Header siteName="Top 6 Richest Companies in the World" 
      authorName="Project by Sidharth Ananthasivagurunathan"/>

    <Companybox :companies="companies"  />

  </div>
</template>
<script>



//import HelloWorld from './components/HelloWorld.vue'
// 1
import Header from './components/Header.vue'
import Companybox from './components/Companybox.vue'


// data url: http://localhost:5555/companies , this might be different for you
export default {
  name: 'App',
  components: {
    // 2 register the component 
    Header,
    Companybox
  },

  data(){
    return {
      companies: []
    }
  },
  methods: {
    // promises

      async fetchCompanies(){
        //  const res= await fetch('http://localhost:5555/companies')
        const res= await fetch('https://sidharthfinalprojectonwebdb.herokuapp.com/api')
         const data= await res.json()
        console.log(data)
         return data
      }

  },

  async created(){
    this.companies = await this.fetchCompanies()
    console.log(this.companies);
  }
}
</script>



<style>


@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Montserrat', sans-serif;
}
.container {
  max-width: 400px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 0.3em solid black;
  padding: 30px;
  border-radius: 5px;
}

div{
  margin-bottom: 0.5em;
}



</style>


