<template>
    <div class="prize-card">
        <div class="prize-card-container">
            <h4>Win a {{prize.name}}</h4>
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
    /* .prize-card {
        flex-grow: 1;
    } */
</style>


