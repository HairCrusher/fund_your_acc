<template>
    <div class="inner">
        <span>From</span>
        <v-select
                filled
                :items="exchange"
                placeholder="Choose exchange"
        />
        <span>To</span>
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
            class="amount"
            filled
            placeholder="Choose amount"
            type="number"
            :rules="[(v) => v]"
        >
            <template v-slot:message>
                <v-card class="message">
                    <v-card-text>
                        <v-chip class="mb-2" color="#eaf0f4" text-color="primary" label>Balance: 0.12341234</v-chip>
                        <div>
                            <v-chip color="alpha" label>10%</v-chip>
                            <v-chip color="alpha" label>25%</v-chip>
                            <v-chip color="alpha" label>50%</v-chip>
                            <v-chip color="alpha" label>100%</v-chip>
                            <v-chip color="alpha" label>Split</v-chip>
                        </div>
                    </v-card-text>
                </v-card>
            </template>
        </v-text-field>



        <v-btn block large color="primary">Rebalance</v-btn>
    </div>
</template>

<script>
    export default {
        name: "Rebalance",
        data() {
            return {
                exchange: ['Kraken', 'Kraken2', 'Kraken3'],
                currency: ['currency1', 'currency2', 'currency3']
            }
        }
    }
</script>

<style lang="scss" scoped>
    .inner {
        text-align: left;
    }
    .message {
        .v-chip {
            font-weight: bold;
            margin-right: 1rem;
        }

        div .v-chip {
            color: #fff;
        }

        .balance {

        }
    }
</style>