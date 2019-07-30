<template>
    <div>
        <h1>Side bar</h1>
        <div class=sidebar>
            <a v-bind:key="item.id" v-for="item in sidebar">{{item.msg}}</a>
        </div>
    </div>
</template>

<script>
export default {
    name:"Sidebar",
    data() {
        return {
            sidebar: [
                {
                    id: 1,
                    msg:"Option 1"
                },
                {
                    id:2,
                    msg:"Option 2"
                },
                {
                    id: 3,
                    msg:"Option 3"
                }
            ]
        }
    }
}
</script>

<style scoped>
a {
    padding: 6px 8px 6px 16px;
    text-decoration: none;
    font-size: 25px;
    color: #818181;
    display: block;
}

.sidebar {
    height: 100%;
    width: 160px;
    position: fixed;
    z-index: 1;
    top: 0;
    left: 0;
    background-color: #111;
    overflow-x: hidden;
    padding-top: 20px;
}
</style>
