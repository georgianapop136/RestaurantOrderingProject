<template>
    <div id="app">
        <div v-if="admin">
            <router-view></router-view>
        </div>
        <div v-else>
            <NavBar />

            <div class="auth-wrapper">
                <div class="auth-inner">
                    <router-view></router-view>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import NavBar from './components/NavBar.vue';
import { mapActions } from 'vuex';
import { mapState } from 'vuex';
export default {
    name: 'App',
    components: {
        NavBar
    },

    // created() {
    //     this.getFoodsData()
    // },

    mounted() {
        this.getFoodsData()
    },

    computed: {
        ...mapState(["admin"])
    },

    methods: {
        ...mapActions(["getFoodsData"])
    }
}
</script>

<style>
@import "./assets/css/global_style.css";
</style>

