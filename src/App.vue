<template>
  <ul>
    <learning-resource v-for="resource in storedResources" :key="resource.id" :title="resource.title" :description="resource.description" :link="resource.link">
       
    </learning-resource>
    <stored-resources :resources="storedResources"></stored-resources>
  </ul>
</template>
<script>


import StoredResources from './components/learning-resources/StoredResources.vue';

export default {
    components:{
        StoredResources
    },
    data(){
        return{
            storedResources:[
                {
                    id: 'official-guide', title: 'Official Guide', description: 'the official Vue.js documented.',link: 'https://vuejs.org'
                },
                {
                    id: 'google',title:'Google', description: 'the official Vue.js documented.',link: 'https://google.org'
                }
            ]
        }
    }
}
</script>
<style >
     @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

    * {
    box-sizing: border-box;
    }

    html {
    font-family: 'Roboto', sans-serif;
    }

    body {
    margin: 0;
    }
      
</style>