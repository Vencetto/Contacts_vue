<template>
  <header>
    <h3>{{ title }}</h3>
    <add-button> </add-button>
  </header>
</template>

<script>
import Fav from './AddButon';

export default {
  name: 'Header',
  data: function() {
    return {
      title: "Contacts",
    };
  },
  components: {
    'add-button':Fav,
  }
};
</script>

<style scoped>
header {
  background-color: #e8aa8c;
  margin: auto 0px 30px;
  padding: 16px 32px;
  box-shadow: 0 0 10px 0 rgba(0, 0, 0, 0.3);
}
header p {
  font-size: 29px;
}
</style>