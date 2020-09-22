<template>
    <div>
        <div class='contact__short'>
            <h1>{{lName + ", " + fName + " (" + age + " years)"}} </h1>
            <p class="p__profession">{{profession}}</p>
            <p class="p__email">{{email}}</p>
        </div>
    </div>
</template>

<script>
export default {
    name:'ContactShort',
    props: {
        fName: String,
        lName: String,
        profession: String,
        email: String,
        age: String
    }
}
</script>

<style scoped>
.contact__short{
    /* border: solid 1px rgba(232, 170, 140, 0.4); */
    border-radius: 8px;
    margin: 10px auto;
    padding: 30px 40px;
    background-color: #e2dcd5;
}
.p__profession{
    font-style: italic;
}
.p__email{
    text-decoration: underline;
    font-weight: 600;
    font-style: italic;
}
</style>