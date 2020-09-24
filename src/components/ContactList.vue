<template>
  <div class="contact__list">
    <modal-ask
      v-if="showModal"
      v-on:delete-approved="deleteContact"
      v-on:delete-declined="showHideModal"
    ></modal-ask>
    <new-contact-input
      v-if="showInput"
      v-on:submit-user-create="addContact"
      v-on:close-input="showHideInput"
    ></new-contact-input>
    <add-button v-on:click.native="showHideInput"></add-button>
    <contact-short
      v-for="(item, key) in contactColl"
      v-bind:key="key"
      v-bind:id="key"
      v-bind:lName="item.lName"
      v-bind:fName="item.fName"
      v-bind:email="item.email"
      v-bind:profession="item.profession"
      v-bind:age="item.age"
      v-on:save-id="saveId"
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
    contactColl: {},
  },
  data: function () {
    return {
      showInput: false,
      showModal: false,
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
    // this fucn pass task up to parent component
    addContact: function (newContactObj) {
      this.showHideInput();
      this.$emit('create-contact', newContactObj);
    },
    showHideInput: function () {
      // shoes or disables input window
      this.showInput = !this.showInput;
    },
    saveId: function (id) {
      this.showHideModal();
      this.deleteId = id;
    },
    showHideModal: function () {
      // shows or disables modal window
      this.showModal = !this.showModal;
    },
    // this fucn pass task up to parent component
    deleteContact: function() {
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