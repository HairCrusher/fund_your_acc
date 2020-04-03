<template>
    <div class="inner">
        <v-select
                filled
                :items="exchange"
                :value="exchange[0]"
                placeholder="Choose exchange"
        />
        <v-select
                filled
                :items="currency"
                placeholder="Choose currency"
        />

        <v-img src="@/assets/qr.png" width="120"/>

        <p class="account-id">FGHsajdbkjghaSJHgjkadbajkasdjkJABKkj</p>

        <v-btn block large color="primary">Copy</v-btn>
    </div>
</template>

<script>
    export default {
        name: "Deposit",
        data() {
            return {
                exchange: ['Kraken', 'Kraken2', 'Kraken3'],
                currency: ['currency1', 'currency2', 'currency3']
            }
        }
    }
</script>

<style scoped>
    .v-image {
        margin: auto;
    }

    .account-id {
        font-size: 16px;
        margin-top: 20px;
    }
</style>