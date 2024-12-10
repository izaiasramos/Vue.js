<template>
   <CommentsVue/>
  <testStructure msg="boooa"/>
</template>

<script>
  import CommentsVue from './components/CommentsVue.vue';
  import testStructure from './components/testStructure.vue' 
  export default {
    name: 'App',
    components: {
      CommentsVue,
      testStructure
    }
  }
</script>

<style>
</style>
