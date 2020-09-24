<template>
  <div id="app">
    <local-header></local-header>
    <contact-list
      v-bind:contactColl="store"
      v-on:delete-contact="deleteContact"
      v-on:create-contact="addContact"
    ></contact-list>
  </div>
</template>

<script>
import Header from "@/components/Header";
import store from "@/store/store";
import ContactList from "@/components/ContactList";

export default {
  name: "App",
  components: {
    "local-header": Header,
    "contact-list": ContactList,
  },
  data: function () {
    return {
      store: store,
    };
  },
  methods: {
    deleteContact: function (id) {
      delete(this.store[id]);
    },
    addContact: function (newContactObj) {
      this.store[String(this.createId())] = newContactObj;
    },
    createId: function() {
      // creates pseudo hash for Id
      return '_' + Math.random().toString(36).substr(2, 9);
    }
  },
};
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
