<template>
    <div id="app">
        @{{ user.username }} - {{ fullName }}<br/>
        <strong>Followers:</strong> {{ followers }}<br/>
        <button v-on:click="followUser">
            Follow
        </button>
    </div>
</template>

<script>
    export default {
        name: 'App',
        data() {
            return {
                followers: 0,
                user: {
                    id: 1,
                    username: 'jeffersonsimaogoncalves',
                    firstName: 'Jefferson',
                    lastName: 'Simão Gonçalves',
                    email: 'gerson.simao.92@gmail.com',
                    isAdmin: true
                }
            };
        },
        computed: {
            fullName() {
                return `${this.user.firstName} ${this.user.lastName}`;
            }
        },
        methods: {
            followUser() {
                this.followers++;
            }
        },
        mounted() {
            this.followUser();
        }
    }
</script>

<style>
    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>
