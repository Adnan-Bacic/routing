<template>
    <div class="main-nav">
        <ul>
            <li><a href="/">Home</a></li>
            <li><a href="/">About</a></li>

            <li><router-link to="/">Home</router-link></li>
            <li><router-link :to="{ name:'About' }">About</router-link></li>
        </ul>
        <h2>User profiles</h2>
        <ul>
            <li v-for="(id, index) in userIDS" v-bind:key="index">
                <router-link :to="{ name: 'ViewProfile', params:{ user_id: id }}">
                    <span>Profile: {{ id }}</span>
                </router-link>
            </li>
        </ul>
        <h2>Navigation controls</h2>
        <ul>
            <li><button v-on:click="goBack">Go back</button></li>
            <li><button v-on:click="goHome">Redirect to home</button></li>
            <li><button v-on:click="goForward">Go forward</button></li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'Navbar',

    data(){
        return{
            userIDS: ['1', '2', '3', '4']
        }
    },
    methods:{
        goHome(){
            this.$router.push({ name: 'HelloWorld' })
        },
        goBack(){
            this.$router.go( -1 )
        },
        goForward(){
            this.$router.go( +1 )
        }
    }
}
</script>

<style scoped>
    ul{
        list-style-type: none;
        padding: 0;
    }
    a{
        color: #42b983;
    }
    li{
        display: inline-block;
        margin: 10px;
    }
    a.router-link-exact-active{
        color: purple;
    }
</style>