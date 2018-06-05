<template>
    <div>
        <div class="ui secondary pointing menu">
            <router-link to="/" class="active item">Image Store</router-link>

            <div class="right menu">
                <div class="horizontal" v-if="isLoggedIn">
                    <router-link to="/" class="ui item">Galleries</router-link>
                    <router-link to="/upload" class="ui item">Upload</router-link>
                    <a class="ui item" @click="logout">Logout</a>
                </div>
                <a v-if="!isLoggedIn" @click="login" class="ui item">Login</a>
            </div>
        </div>
    </div>
</template>

<script>
import { mapActions, mapGetters } from 'vuex';

export default {
    name: 'AppHeader',
    computed: mapGetters(['isLoggedIn']),
    methods: mapActions(['login', 'logout'])
}

</script>

<style>
    .horizontal {
        display: flex;
        flex-direction: row;
    }
</style>


