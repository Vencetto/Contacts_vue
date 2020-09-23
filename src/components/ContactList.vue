<template>
    <div class='contact__list'>
        <add-button v-on:click="showModal"> </add-button>
        <contact-short v-for="con of contactArr" v-bind:key="con.id"
            v-bind:lName="con.lName" v-bind:fName="con.fName" v-bind:email="con.email" v-bind:profession="con.profession" v-bind:age="con.age">
        </contact-short>
    </div>
</template>

<script>
import AddButton from '@/components/AddButton';
import ContactShort from '@/components/ContactShort';

export default {
    name: 'ContactList',
    props: {
        contactArr:{}
        },
    components: {
        'contact-short': ContactShort,
        'add-button': AddButton
    },
    methods: {
        addContact: function() {

        },
        showModal: function() {

        }
    }
}

</script>

<style scoped>
.contact__list{
    width: 800px;
    margin: auto;
    position: relative;
}
.img__add-wrapper{
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
.img__add-wrapper:hover{
   box-shadow: 3px 3px 3px rgba(232, 170, 140, 0.4);
}
</style>