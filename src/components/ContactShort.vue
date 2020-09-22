<template>
    <div>
        <div class='contact__short'>
            <p>{{"Name " + fName}}</p>
            <p>{{"Surname " + lName}}</p>
            <p>{{"Proffesion " + proffesion}}</p>
            <p>{{"email " + email}}</p>
        </div>
    </div>
</template>

<script>
export default {
    name:'ContactShort',
    props: {
        fName: String,
        lName: String,
        proffesion: String,
        email: String
    }
}
</script>

<style scoped>
.contact__short{
    border: solid 2px ;
}
</style>