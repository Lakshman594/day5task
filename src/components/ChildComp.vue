<template>
<h1>Hii Good Morning </h1>
<p >{{detail.title}}</p>
<p >{{detail.description}}</p>
<div><button @click.prevent="$emit('editData',detail.title)">Edit Data</button></div>
<hr />
</template>

<script setup>
import { defineProps } from 'vue';

 const props = defineProps({
    detail:{
       type: Object,
       required:true
    }
})

console.log(props.detail.title)
</script>