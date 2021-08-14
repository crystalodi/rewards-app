<template>
    <p>Here is the full list of prizes that you can win.</p>
    <div class="prizes-container" v-if="prizes">
        <PrizeCard v-for="prize of prizes" :key="prize.id" :prize="prize"/>
    </div>
</template>

<script>
import PrizeCard from "../components/PrizeCard.vue";
export default {
    name: "PrizeList",
    components: {
        PrizeCard
    },
    props: ["prizes"],
    created () {
        console.log(this.prizes);
    },
}
</script>

<style>
    .prizes-container {
        display: grid;
    }
</style>