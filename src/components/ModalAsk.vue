<template>
    <div class="modal__container">
        <h1>{{ title }}</h1>
        <div class="buttons__wrapper">
            <button class="approve__button" v-on:click="$emit('delete-approved')">
            </button>
            <button class="decline__button" v-on:click="$emit('delete-declined')">
            </button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'modalAsk',
    data: function() {
        return {
            title: 'Sure?'
        }
    }   
}
</script>

<style scoped>
.buttons__wrapper {
  margin: 10px 25px;
  display: flex;
  justify-content: space-between;
}
.modal__container h1 {
  color: #5e616a;
  text-align: center;
  margin-bottom: 20px;
}
.modal__container {
  position: fixed;
  background-color: #e8aa8c;
  border-radius: 8px;
  padding: 20px 30px;
  z-index: 10;
  margin: 150px 319px;
  border: solid 1px#5e616a;
}
.decline__button{
    border-radius: 4px;    
    margin-left: 10px;
    width: 35px;
    height: 35px;
    background-image: url('../../public/cancel.svg');
    outline: none;
    background-color: #e8aa8c;
    border: none;
}
.decline__button:hover{
    cursor: pointer;
    box-shadow: 3px 3px 3px 3px rgba(94, 97, 106, 0.4);
}
.approve__button{
    border-radius: 4px;
    margin-right: 10px;
    width: 35px;
    height: 35px;
    background-image: url('../../public/check.svg');
    outline: none;
    background-color: #e8aa8c;
    border: none;
}
.approve__button:hover{
    cursor: pointer;
    box-shadow: 3px 3px 3px 3px rgba(94, 97, 106, 0.4);
}
</style>