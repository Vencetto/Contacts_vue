<template>
  <div>
    <div class="contact__short">
        <div class="header__wrapper">
            <h1 v-if="age">{{lName + ", " + fName + " (" + age + " years)"}}</h1>
            <h1 v-else>{{lName + ", " + fName}}</h1>
            <button class="close__button"></button>
        </div>
      <p class="p__profession">{{profession}}</p>
      <div class="bottom__wrapper">
        <p class="p__email">{{email}}</p>
        <a class="more__link" href="">Read more</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ContactShort",
  props: {
    fName: String,
    lName: String,
    profession: String,
    email: String,
    age: String,
  },
};
</script>

<style scoped>
*{
    color: #5e616a;
}
.contact__short {
  border-radius: 8px;
  margin: 10px auto;
  padding: 30px 40px;
  background-color: #e2dcd5;
}
.p__profession {
  font-style: italic;
}
.p__email {
  text-decoration: underline;
  font-weight: 600;
  font-style: italic;
  margin: 0;
}
.header__wrapper{
    display: flex;
    justify-content: space-between;
}
.close__button{
    width: 25px;
    height: 25px;
    background-image: url('../../public/cancel.svg');
    outline: none;
    background-color: #e2dcd5;
    border: none;
}
.close__button:hover{
    cursor: pointer;
    box-shadow: 3px 3px 3px 3px rgba(232, 170, 140, 0.4);
}
.bottom__wrapper{
    display: flex;
    justify-content: space-between;
}
.more__link{
    margin-top: 5px;
}
</style>