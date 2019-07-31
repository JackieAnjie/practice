<template>
    <div>
        <h1>Side bar</h1>
        <div class=sidebar>
            <searchBar v-on:click="showPage"/>
            <div v-bind:key="item.title" v-for="item in categories">
                <a v-on:click="expand(item)">
                    <a v-if="item.clicked">&#x2BC6; {{item.title}}</a>
                    <a v-else> &#x2BC8; {{item.title}}</a>
                </a>
                <a v-if="item.clicked">
                    <a class="suboption" v-bind:key="subitem.title" v-for="subitem in item.suboption" v-on:click="showPage(subitem.title)">{{subitem.title}}</a>
                </a>
            </div>
        </div>
        <Content v-bind:selected="selected"/>
    </div>
</template>

<script>
import searchBar from './SearchBar';
import Content from './Content';

export default {
    name:"Sidebar",
    components: {
        searchBar,
        Content
    },
    data() {
        return {
            selected: "Pick an option!",
            categories: [
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
            this.selected = option
        }
    }
}
</script>

<style>
a {
    padding: 6px 8px 6px 6px;
    text-decoration: none;
    font-size: 25px;
    color: #818181;
    display: block;
}

.sidebar a:hover, 
.active {
  color: #f1f1f1;
}

.suboption {
    font-size: 16px;
    margin-left: 33px;
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
