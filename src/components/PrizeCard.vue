<template>
    <div class="col-xl-4 col-md-6 col-12">
        <div class="card prize-card">
            <img class="card-img-top" v-bind:src="prize.image_url" v-if="prize.image_url"/>
            <div class="card-body">
                <div class="card-title">Win a {{prize.name}}
                </div>
                <router-link :to="`/prize/${prize.id}`" tag="a" class="card-link">View Details</router-link>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "PrizeCard",
    props: ["prize"]
}
</script>
<style>
    image {
        width: 100%;
    }
    .prize-card {
        border: 0!important;
    }
</style>


