<template>
  <ChildComp v-for="detail in details" :key="detail.title" :detail="detail" @editData="updateData"/>
</template>

<script setup>
import ChildComp from './components/ChildComp.vue';
import {ref} from 'vue'


const details = ref([{title:'lets learn props1',description:"Props are used to change data of child component by parent component1"},
{title:'lets learn prop2',description:"Props are used to change data of child component by parent component2"},
{title:'lets learn props3',description:"Props are used to change data of child component by parent component3"}])

const updateData = (DataId)=>{
  details.value = details.value.map(detail=>{
    if(detail.title == DataId){
      return  {...detail, description:'Data is updated'}
    }
    return detail
    
  })
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
