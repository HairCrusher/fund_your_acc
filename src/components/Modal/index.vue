<template>
    <div class="text-center">
        <v-dialog
                v-model="dialog"
                max-width="790"
        >
            <v-card>
                <v-card-title>
                    <v-tabs v-model="activeTab" color="dark">
                        <v-tab
                                v-for="tab in tabs"
                                :key="tab.title"
                                :href="`#tab-${tab.title}`"
                        >{{tab.title}}
                        </v-tab>
                    </v-tabs>
                </v-card-title>

                <v-card-text>
                    <v-tabs-items v-model="activeTab">
                        <v-tab-item
                                v-for="tab in tabs"
                                :key="tab.title"
                                :value="`tab-${tab.title}`"
                        >
                            <component :is="tab.component"/>
                        </v-tab-item>
                    </v-tabs-items>
                </v-card-text>

            </v-card>
        </v-dialog>
    </div>
</template>

<script>
    export default {
        name: "Modal",
        data() {
            return {
                dialog: false,
                activeTab: null,
                tabs: [
                    {title: 'Deposit', component: () => import('./Deposit')},
                    {title: 'Withdraw', component: () => import('./Withdraw')},
                    {title: 'Rebalance', component: () => import('./Rebalance')},
                ]
            }
        },
        mounted() {
            this.$eventBus.$on('modal', status => this.dialog = status);
        },
        destroyed() {
            this.$eventBus.$off('modal');
        }
    }
</script>

<style scoped>
    .inner {
        max-width: 380px;
        margin: auto;
        padding-top: 25px;
        padding-bottom: 30px;
        text-align: center;
    }
</style>