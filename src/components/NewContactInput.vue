<template>
 <div class="input__container">
     <div class="top__wrapper">
        <h1>New Contact</h1>
        <button class="close__button"></button>
     </div>
     <input class="input__item" placeholder="First Name">
     <input class="input__item" placeholder="Last Name">
     <input class="input__item" placeholder="Profession">
     <input class="input__item" placeholder="Email">
     <input class="input__item" placeholder="Age">
     <input class="input__item" placeholder="Phone">
 </div>    
</template>

<script>
export default {
    name:'NewContactInput'
}
</script>

<style scoped>
.top__wrapper h1 {
  color: #5e616a;
  text-align: center;
  margin: 0;
}
.input__container{
    position: fixed;
    background-color: #e8aa8c;
    border-radius: 8px;
    padding: 20px 30px;
    z-index: 5;
    margin: 150px 230px;
}
.input__item{
    margin: 20px 20px 20px 10px;
    display: block;
    width: 150px;
    height: 25px;
    outline: none;
    border: none;
    border-radius: 6px 6px 6px 6px;
    padding: 5px;
    font-size: 18px;
    transition: ease-in 7;
}
.top__wrapper{
    margin: 10px 25px;
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
</style>