<template>
    <div>
        <input type="text" v-model="search" placeholder="search box"/>
        <div v-if="this.search != ''">
            <div v-if="filteredLinks.length!=0">
                <a class="suboption" v-bind:key="option.title" v-for="option in filteredLinks" v-on:click="showPage(option.title)">
                    {{option.title}}
                </a>
            </div>
            <a class="suboption" v-else>
                No Results
            </a>
        </div>
    </div>
</template>

<script>
export default {
    name: "SearchBar",
    data() {
        return {
            search:'',
            options: [
                {
                    title:"Option 1a"
                },
                {
                    title:"Option 1b"
                },
                {
                    title:"Option 2a"
                },
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
    },
    computed:{
        filteredLinks: function(){
            return this.options.filter((option)=>{
                return option.title.match(this.search);
            });
        }
    }
}
</script>

<style>

</style>
