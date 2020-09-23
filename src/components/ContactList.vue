<template>
  <div class="contact__list">
    <new-contact-input
      v-if="showInput"
      v-on:submit-user-create="addContact"
      v-on:close-input="showInput = !showInput"
    ></new-contact-input>
    <add-button v-on:click.native="showInput = !showInput"></add-button>
    <contact-short
      v-for="con of contactArr"
      v-bind:key="con.id"
      v-bind:lName="con.lName"
      v-bind:fName="con.fName"
      v-bind:email="con.email"
      v-bind:profession="con.profession"
      v-bind:age="con.age"
    ></contact-short>
  </div>
</template>

<script>
import AddButton from "@/components/AddButton";
import ContactShort from "@/components/ContactShort";
import NewContactInput from "@/components/NewContactInput";

export default {
  name: "ContactList",
  props: {
    contactArr: {},
  },
  data: function () {
    return {
      showInput: false,
    };
  },
  components: {
    "contact-short": ContactShort,
    "add-button": AddButton,
    "new-contact-input": NewContactInput,
  },
  methods: {
      // it needs to change id in this place so they won't duplicate or etc.
    addContact: function (newContactObj) {
        newContactObj.id = this.contactArr.length;
      return this.contactArr.push(newContactObj);
    },
  },
};
</script>

<style scoped>
.contact__list {
  width: 800px;
  margin: auto;
}
.img__add-wrapper {
  position: fixed;
  width: 55px;
  height: 55px;
  right: 0;
  bottom: 0;
  margin-right: 100px;
  margin-bottom: 100px;
  cursor: pointer;
  border-radius: 50%;
}
.img__add-wrapper:hover {
  box-shadow: 3px 3px 3px rgba(232, 170, 140, 0.4);
}
</style>