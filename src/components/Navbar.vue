<template>
    <nav class="main-nav">
        <ul>
            <li><router-link to="/">Home</router-link></li>
            <li><router-link :to="{name : 'About'}">About</router-link></li>
        </ul>
        <h2>user Profile</h2>
        <ul>
            <li v-for="(id, index) in userIds" :key="index">
            <router-link :to="{ name: 'ViewProfile',params:{ user_id: id}}" >
                <span>Profile {{ id }}</span>
            </router-link>
            </li>
        </ul>
        <h2>Navigations Control</h2>
        <ul>
            <li><button @click="goback">Go Back</button></li>
            <li><button @click="gohome" >Redirect to Home</button></li>
            <li><button @click="goForward">Go Forward</button></li>
        </ul>
    </nav>
</template>
<script>
export default {
    name:'Navbar',
    data(){
        return{
            userIds:['1','2','3','4']

        }
    },
    methods:{
        gohome(){
            this.$router.push({ name: 'Home'})
        },
        goback(){
            this.$router.go(-1)

        },
          goForward(){
            this.$router.go(+1)

        }
    }
}
</script>
<style>
ul{
    list-style-type: none;
    padding:0;
}
a{
    color:#42b983;
}
li{
    display:inline-block;
    margin:10px;
}
.router-link-active{
    color:purple;
}
</style>