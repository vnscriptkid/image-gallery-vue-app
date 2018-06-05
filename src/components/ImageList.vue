<template>  
    <div>
    <div v-if="isLoggedIn" class="image-container">
        <img v-for="image in allImages" v-bind:src="image.link" v-bind:key="image.id" />
    </div>
    <div v-else>
        <h1>Log in to get started</h1>
    </div>
    </div>
    
</template>

<script>
import { mapActions, mapGetters } from 'vuex';

export default {
    name: 'ImageList',
    computed: mapGetters(['allImages', 'isLoggedIn']),
    methods: mapActions(['fetchImages']),
    created() {
        this.fetchImages();
    }
}
</script>

<style scoped>
    .image-container {
        column-count: 3;
        column-gap: 0;
    }

    img {
        max-width: 100%;
        padding: 5px;
    }
</style>


