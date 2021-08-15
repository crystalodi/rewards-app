<template>
    <div class="prize-detail-container">
        <div class="card app-card prize-card" v-if="prizeFound">
            <div class="row">
                <div class="col-4">
                    <img :src="prize.image_url" class="img-fluid"/>
                </div>
                <div class="col-8">
                    <div class="card-body">
                        <div class="card-title">
                            <h5>{{prize.name}}</h5>
                        </div>
                        <div class="card-text mb-3">
                            {{prize.description}}
                            <p>Quantity: {{prize.quantity}}</p>
                        </div>
                        <button class="app-button redeem-this me-1" @click="confirmRedeemPrize()" :disabled="prize.quantity === 0">Redeem This Prize</button>
                        <button class="app-button go-back" @click="goBackToPrizes()">Go Back To Prizes</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: "PrizeDetail",
    props: ["prizes"],
    emits: ["updatePrize"],
    methods: {
        redeemPrize() {
            console.log("emit", this.$route.params.id);
            this.$emit('updatePrize', this.$route.params.id);
        },
        confirmRedeemPrize() {
            // show lightbox
        },
        goBackToPrizes() {
            this.$router.push({
                path: "/"
            });
        }
    },
    computed: {
        prize() {
            return this.prizes?.find(prize => prize.id === this.$route.params.id)
        },
        prizeFound() {
            return !!this.prize;
        }
    }
}
</script>

<style>
    .prize-detail-container {
        display: flex;
        align-content: center;
        justify-content: center;
    }
    .redeem-this {
        background-color:#ffce0a;
    }
    .redeem-this:hover {
        background-color: #ffd324;
    }
    .go-back {
        background-color:#0274bb;
    }
    .go-back:hover {
        background-color: #0da1fc;
    }
</style>