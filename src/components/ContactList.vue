<template>
    <div class='contact__list'>
        <contact-short v-for="con of contactArr" v-bind:key="con.id"
            v-bind:lName="con.lName" v-bind:fName="con.fName" v-bind:email="con.email">
        </contact-short>
    </div>
</template>

<script>
import ContactShort from '@/components/ContactShort';

export default {
    name: 'ContactList',
    props: {
        contactArr:{}
        },
    components: {
        'contact-short': ContactShort
    }
}

</script>

<style scoped>

</style>