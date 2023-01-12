<script>
export default {
    props: {
        menu: Array
    }
}
</script>
<template>
    <div class="background">
        <div id="jumbotron">
        </div>
        <div class="album">
            <div class="album-card" v-for="(item, index) in menu" :key="index">
                <div class="album-image">
                    <img :src="item.thumb" :alt="item.series">
                </div>
                <h4>{{ item.series }}</h4>
            </div>
        </div>
        <button class="button_load">Load more</button>
    </div>
</template>

<style lang="scss">
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;

.background {
    background-color: #1c1c1c;
    text-align: center;

    .button_load {
        margin-bottom: 3em;
        color: white;
        padding: 1em 2em;
        background-color: #0282f9;
        border: none;
        cursor: pointer;
        @include upbold
    }
}

#jumbotron {
    height: 20rem;
    background-image: url('/img/jumbotron.jpg');
    background-size: cover;

}

div.album {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
    position: relative;
    padding: 4rem 0;

    div.album-card {
        width: calc((100% / 6) - 1rem);

        h4 {
            margin: 1rem 0;
            color: white;
        }

        div.album-image {
            width: 100%;
            height: 10rem;
            overflow: hidden;

            img {
                width: 100%;
            }
        }
    }

    &::before {
        content: 'Current series';
        display: flex;
        justify-content: center;
        align-items: center;
        position: absolute;
        text-transform: uppercase;
        font-weight: bold;
        top: 0;
        left: 0;
        transform: translateY(-50%);
        width: 12rem;
        height: 4rem;
        background-color: #0282f9;
    }
}
</style>