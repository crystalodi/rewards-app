<template>
    <div class="col-xl-4 col-md-6 col-12">
        <div class="card prize-card mb-5">
            <img class="card-img-top" v-bind:src="prize.image_url" v-if="prize.image_url"/>
            <div class="card-body text-center">
                <div class="card-title mb-5">
                    <b>Win a {{prize.name}}</b>
                </div>
                <button class="redeem-button" @click="goToRedeem()">Redeem ></button>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: "PrizeCard",
    props: ["prize"],
    methods: {
        goToRedeem() {
            this.$router.push({ name: "PrizeDetail", params: { id: this.prize.id }})
        }
    },
}
</script>
<style>
    image {
        width: 100%;
    }
    .prize-card {
        border: 0!important;
        box-shadow: 0 4px 8px 0 rgb(0 0 0 / 20%), 0 6px 20px 0 rgb(0 0 0 / 19%);
    }
    .redeem-button {
        background-color:#ffce0a;
        color:black;
        border:none;
        padding:7px 30px 7px 30px;
        margin:10px;
        font-size: 12px;
        border-radius: 20px;
    }
    .redeem-button:hover {
        background-color: #ffd324;
    }
</style>


