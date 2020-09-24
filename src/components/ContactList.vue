<template>
  <div class="contact__list">
    <modal-ask
      v-if="showModal"
      v-on:delete-approved="deleteContactYes"
      v-on:delete-declined="showHideModal"
    ></modal-ask>
    <new-contact-input
      v-if="showInput"
      v-on:submit-user-create="addContact"
      v-on:close-input="showHideInput"
    ></new-contact-input>
    <add-button v-on:click.native="showHideInput"></add-button>
    <contact-short
      v-for="con of contactArr"
      v-bind:key="con.id"
      v-bind:id="con.id"
      v-bind:lName="con.lName"
      v-bind:fName="con.fName"
      v-bind:email="con.email"
      v-bind:profession="con.profession"
      v-bind:age="con.age"
      v-on:delete-contact="deleteContact"
    ></contact-short>
  </div>
</template>

<script>
import AddButton from "@/components/AddButton";
import ContactShort from "@/components/ContactShort";
import NewContactInput from "@/components/NewContactInput";
import ModalAsk from "@/components/ModalAsk";

export default {
  name: "ContactList",
  props: {
    contactArr: {},
  },
  data: function () {
    return {
      showInput: false,
      showModal: false,
      needDelete: false,
      deleteId: null
    };
  },
  components: {
    "contact-short": ContactShort,
    "add-button": AddButton,
    "new-contact-input": NewContactInput,
    "modal-ask": ModalAsk,
  },
  methods: {
    addContact: function (newContactObj) {
      this.showHideInput();
      // it needs to change id here so contacts won't duplicate or etc.
      // newContactObj.id = this.contactArr.length;
      return this.contactArr.push(newContactObj);
    },
    showHideInput: function () {
      // shoes or disables input window
      this.showInput = !this.showInput;
    },
    deleteContact: function (id) {
      this.showHideModal();
      this.deleteId = id;
      // if (this.needDelete)
      //   this.$emit('delete-contact', id);
    },
    showHideModal: function () {
      // shows or disables modal window
      this.showModal = !this.showModal;
    },
    deleteContactYes: function() {
      this.$emit('delete-contact', this.deleteId);
      this.showHideModal();
    }
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