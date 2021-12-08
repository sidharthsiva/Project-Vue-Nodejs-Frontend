<template>
    <!--div v-if="company.published == false"-->

    <!-- <div :class="company.published ? 'green': 'red' "> -->

    <div>
    
    <h2>{{company.company}}</h2>
    <h3>{{company.marketcap}}</h3>
    <h4>{{company.industry}}</h4>
    <h5> {{company.product}}</h5>


    </div>
</template>

<script>

export default{
    name: 'company',
    props:{
        company : JSON
    }
}
</script>

<style scoped>



h4{
    margin: 2px;
}

div{
    background-color: #fdeca1;
    color: black;
    padding: 1em;
}

.red{
background-color: orangered !important;

}


</style>