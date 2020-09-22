<template>
  <header>
    <h1>
      <img class="img__book" src="../../public/book.svg" alt="">
      {{ title }}
      </h1>
  </header>
</template>

<script>

export default {
  name: 'Header',
  data: function() {
    return {
      title: "Contacts Book",
    };
  }
};
</script>

<style scoped>
header {
  background-color: #e8aa8c;
  margin: auto 0px 30px;
  padding: 16px 60px;
  box-shadow: 0 0 10px 0 rgba(0, 0, 0, 0.3);
}
header h1 {
  font-family: 'Inconsolata', monospace;
  font-weight: 500;
  font-size: 40px;
  color: #5e616a;
}
.img__book{
  width: 40px;
  height: 40px;
  margin-bottom: -7px;
}
</style>