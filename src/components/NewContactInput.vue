<template>
  <div class="input__container">
    <div class="top__wrapper">
      <h1>{{ title }}</h1>
      <button class="close__button" v-on:click="$emit('close-input')"></button>
    </div>

    <div class="input__blocks">
      <div class="block__one">
        <input
          class="input__item"
          name="fName"
          v-on:input="changeNewUserData"
          placeholder="First Name"
        />
        <input
          class="input__item"
          name="lName"
          v-on:input="changeNewUserData"
          placeholder="Last Name"
        />
        <input class="input__item" name="email" v-on:input="changeNewUserData" placeholder="Email" />
      </div>

      <div class="block__two">
        <input
          class="input__item"
          name="profession"
          v-on:input="changeNewUserData"
          placeholder="Profession"
        />
        <input class="input__item" name="age" v-on:input="changeNewUserData" placeholder="Age" />
        <input class="input__item" name="phone" v-on:input="changeNewUserData" placeholder="Phone" />
      </div>
    </div>
    <div class="submit__button-wrapper">
      <button
        class="submit__button"
        v-on:click="$emit('submit-user-create', newUserData)"
      >{{ button_text }}</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "NewContactInput",
  data: function () {
    return {
      title: "New contact",
      button_text: "Create",
      newUserData: {
            fName:"",
            lName:"",
            phoneNumber:"",
            profession:"",
            email:"",
            age:""
        },
    };
  },
  methods: {
    changeNewUserData: function (event) {
      return (this.newUserData = {
        ...this.newUserData,
        [event.target.name]: event.target.value,
      });
    },
  },
};
</script>

<style scoped>
.top__wrapper {
  margin: 10px 25px;
  display: flex;
  justify-content: space-between;
  padding-left: 60px;
}
.top__wrapper h1 {
  color: #5e616a;
  text-align: center;
  margin-bottom: 20px;
}
.input__container {
  position: fixed;
  background-color: #e8aa8c;
  border-radius: 8px;
  padding: 20px 30px;
  z-index: 5;
  margin: 150px 230px;
  border: solid 1px#5e616a;
}
.input__item {
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
.input__blocks {
  display: flex;
  justify-content: space-between;
}
.close__button {
  width: 25px;
  height: 25px;
  background-image: url("../../public/cancel.svg");
  outline: none;
  background-color: #e8aa8c;
  border: none;
}
.close__button:hover {
  cursor: pointer;
  box-shadow: 3px 3px 3px 3px rgba(94, 97, 106, 0.4);
}
.submit__button-wrapper {
  margin: 20px 143px;
}
.submit__button {
  width: 95px;
  height: 30px;
  border-radius: 6px;
  background-color: #f9f3e6;
  outline: none;
  border: none;
  font-size: 16px;
  color: #5e616a;
  box-shadow: 2px 2px 2px rgba(94, 97, 106, 0.4);
}
.submit__button:hover {
  cursor: pointer;
  box-shadow: 4px 4px 1px rgba(94, 97, 106, 0.4);
}
</style>