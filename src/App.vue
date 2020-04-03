<template>
    <v-app>
        <AppBar/>
        <Modal/>

        <v-content>
            <v-container>
                <v-btn
                        color="primary"
                        @click="$eventBus.$emit('modal', true)"
                >
                    Open modal
                </v-btn>
            </v-container>
        </v-content>
    </v-app>
</template>

<script>
    import AppBar from "./components/AppBar";
    import Modal from "./components/Modal";

    export default {
        name: 'App',
        components: {
            Modal,
            AppBar,
        }
    };
</script>

<style scoped>
    .v-btn {
        margin-top: 4rem;
    }
    
    .container {
        text-align: center;
    }
</style>
