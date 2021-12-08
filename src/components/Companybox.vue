<template>
    
     <div class="Companybox">
         
        <div v-for="company in companies" :key="company.id" >
                
                <Company :company="company"/>
        </div>

     </div>

</template>

<script>

import Company from "./Company.vue"
export default{

    name: 'Companybox',
    components: {
        Company
    },
    props: {
        companies: JSON
    }

}

</script>


<style>

.Companybox{

    background-color: rgb(164, 250, 175);
    padding: 1em;
    color: gray;
}
</style>