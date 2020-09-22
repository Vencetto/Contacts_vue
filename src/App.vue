<template>
  <div id="app">
    <local-header></local-header>
    <contact-list v-bind:contactArr="store"></contact-list> 
  </div>
</template>

<script>
import Header from '@/components/Header';
import store from "@/store/store";
import ContactList from '@/components/ContactList';

export default {
  name: 'App',
  components: {
    'local-header':Header,
    'contact-list':ContactList
  },
  data: function() {
    return {
      store:store
    };
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;

}
body {
  margin: 0;
  background-color: #f9f3e6;
}
</style>
