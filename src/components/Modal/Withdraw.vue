<template>
    <div class="inner">
        <v-select
                filled
                :items="exchange"
                placeholder="Choose exchange"
        />
        <v-select
                filled
                :items="currency"
                placeholder="Choose currency"
        />

        <v-text-field
            filled
            placeholder="Withdraw amount"
        >
            <template v-slot:append>
                <v-btn color="secondary" depressed>Max</v-btn>
            </template>
        </v-text-field>


        <v-btn block large color="primary">Withdraw</v-btn>
    </div>
</template>

<script>
    export default {
        name: "Withdraw",
        data() {
            return {
                exchange: ['Kraken', 'Kraken2', 'Kraken3'],
                currency: ['currency1', 'currency2', 'currency3']
            }
        }
    }
</script>

<style scoped>
    .v-btn--depressed {
        margin-top: -7px;
    }
</style>