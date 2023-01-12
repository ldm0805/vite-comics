<script>
export default {
    props: {
        menu: Array
    }
}
</script>
<template lang="">
    <header>
        <div id="jumbotron">
        </div>
       <nav>
        <ul>
            <li v-for="(item, index) in menu" :key="index">
                <img :src="item.thumb">
                <h3>{{item.series}}</h3>
            </li>
        </ul>
       </nav>
    </header>
</template>

<style lang="scss">
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;


#jumbotron {
    height: 23rem;
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
    }
}
</style>