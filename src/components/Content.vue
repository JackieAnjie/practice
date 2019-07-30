<template>
    <div>
        <h1>{{title}}</h1>
    </div>
</template>

<script>
export default {
    name:"Content",
    data () {
        return {
            title: "Title",
            description: "This is a description",
            tutorials: "www.google.ca",
            sources: "www.google.ca"
        }
    }
}
</script>

<style scoped>
div {
    margin-left:180px;
}
</style>
