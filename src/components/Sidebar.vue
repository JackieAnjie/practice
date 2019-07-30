<template>
    <div>
        <h1>Side bar</h1>
        <div class=sidebar>
            <div v-bind:key="item.title" v-for="item in sidebar">
                <a v-on:click="expand(item)">
                    <a v-if="item.clicked">&#x2BC6; {{item.title}} </a>
                    <a v-else>&#x2BC8; {{item.title}} </a>
                </a>
                <a v-if="item.clicked">
                    <a v-bind:key="subitem.title" v-for="subitem in item.suboption" v-on:click="showPage(subitem.title)">{{subitem.title}}</a>
                </a>
            </div>
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
                    clicked: false,
                    title:"Option 1",
                    suboption: [
                        {
                            title:"Option 1a"
                        },
                        {
                            title:"Option 1b"
                        }
                    ]
                },
                {
                    clicked: false,
                    title:"Option 2",
                    suboption: [
                        {
                            title:"Option 2a"
                        }
                    ]
                },
                {
                    clicked:false,
                    title:"Option 3",
                    suboption: [
                        {
                            title:"Option 3a"
                        },
                        {
                            title:"Option 3b"
                        },
                        {
                            title:"Option 3c"
                        }
                    ]
                }
            ]
        }
    },

    methods: {
        expand: function(item) {
            if (item.clicked) {
                item.clicked = false
            } else {
                item.clicked = true
            }
        },

        showPage: function(option) {
            alert("you clicked " + option)
        }
    }
}
</script>

<style scoped>
a {
    padding: 6px 8px 6px 6px;
    text-decoration: none;
    font-size: 25px;
    color: #818181;
    display: block;
}

.sidebar a:hover {
  color: #f1f1f1;
}

.active {
    color: #f1f1f1;
}

.sidebar {
    height: 100%;
    width: 11%;
    position: fixed;
    z-index: 1;
    top: 0;
    left: 0;
    background-color: #111;
    overflow-x: hidden;
    padding-top: 20px;
}
</style>
