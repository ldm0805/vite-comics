<script>
import comicsData from "../assets/data/dc-comics.json";
import AppJumbotron from "./AppJumbotron.vue";
import ComicsCard from "./ComicsCard.vue";


export default {
    components: {
        AppJumbotron,
        ComicsCard,
    },
    data() {
        return {
            comics: comicsData
        }
    }
}
</script>

<template>
    <AppJumbotron />
    <div class="dark">
        <div class="container">
            <div class="upper-title">
                <h2 class="title">
                    Comics Series
                </h2>
            </div>
        </div>
        <div class="container">
            <div class="comics-container">
                <ComicsCard v-for="(item, index) in comics" :key="index" :comic="item" />
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;


.dark {
    background-color: #1c1c1c;
}

.upper-title {
    position: relative;

    .title {
        position: absolute;
        top: -40px;
        color: white;
        background-color: $primary;
        width: 200px;
        padding: .2em;
        text-align: center;
        text-transform: uppercase;
    }
}

.comics-container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    padding-top: 5em;
}
</style>
