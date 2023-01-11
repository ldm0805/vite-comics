<script >
export default {
    data() {
        return {
            icon: [
                {
                    label: 'buy-comics-digital-comics.png',
                    url: '#',
                    active: false
                },
                {
                    label: 'buy-comics-merchandise.png',
                    url: '#',
                    active: true
                },
                {
                    label: 'buy-comics-subscriptions.png',
                    url: '#',
                    active: false
                },
                {
                    label: 'buy-comics-shop-locator.png',
                    url: '#',
                    active: false
                },
                {
                    label: 'buy-dc-power-visa.svg',
                    url: '#',
                    active: false
                },
            ]
        }
    },
    methods: {
        getImagePath: function (img) {
            return new URL(`../assets/img/${img}`, import.meta.url).href;
        }
    }
};
</script>

<template>
    <footer>
        <div class="footer_cont">
            <ul>
                <li v-for="(item, index) in icon" :key="index">
                    <img :src="icon.label" alt="loghi">
                </li>
            </ul>
        </div>

        <div class="cols cont_list">
            <div>
                <div class="footer-links">
                    <h4>Dc Comics</h4>
                    <ul>
                        <li><a href="#">Characters</a></li>
                        <li><a href="#">Comics</a></li>
                        <li><a href="#">Movies</a></li>
                        <li><a href="#">TV</a></li>
                        <li><a href="#">Games</a></li>
                        <li><a href="#">Videos</a></li>
                        <li><a href="#">News</a></li>
                    </ul>
                </div>

                <div class="footer-links">
                    <h4>Shop</h4>
                    <ul>
                        <li><a href="#">Shop DC</a></li>
                        <li><a href="#">Shop DC Collectibles</a></li>
                    </ul>
                </div>
            </div>

            <div class="footer-links">
                <h4>DC</h4>
                <ul>
                    <li><a href="#">Temos Of Use</a></li>
                    <li><a href="#">Privacy policy (New)</a></li>
                    <li><a href="#">Ad Choices</a></li>
                    <li><a href="#">Advertising</a></li>
                    <li><a href="#">Jobs</a></li>
                    <li><a href="#">Subscriptions</a></li>
                    <li><a href="#">Talent Workshops</a></li>
                    <li><a href="#">CPSC Cerrificates</a></li>
                    <li><a href="#">Ratings</a></li>
                    <li><a href="#">Shop Help</a></li>
                    <li><a href="#">Contact Us</a></li>
                </ul>
            </div>

            <div class="footer-links">
                <h4>SITES</h4>
                <ul>
                    <li><a href="#">DC</a></li>
                    <li><a href="#">MAD Magazine</a></li>
                    <li><a href="#">DC Kids</a></li>
                    <li><a href="#">DC Universe</a></li>
                    <li><a href="#">DC Power Visa</a></li>
                </ul>
            </div>

            <div class="dc_bg">
                <img src="/img/dc-logo-bg.png" alt="">
            </div>
        </div>
        <div class="social">
            <div class="col-but">
                <button>Sign-up now!</button>
            </div>
            <div class="icon">
                <h3>Follow us</h3>
                <ul>
                    <li>ciao</li>
                </ul>
            </div>
        </div>
    </footer>
</template>

<style lang="scss">
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;



.footer_cont {
    height: 200px;
    background-color: #0282f9;
    display: flex;
    align-items: center;

    .contet_title {
        color: white;
        @include upbold;
    }

    .cont_list {
        color: red;
    }
}

.cont_list {
    padding: 1em;
    background-image: url('/img/footer-bg.jpg');
    background-size: cover;
    display: flex;
    color: $white;

    div {
        padding: 0em 2em;
    }

    li {
        color: $white;
        list-style: $listnone;
    }

    li a {
        color: $gray;
        text-decoration: none;
    }
}

.social {
    height: 100px;
    background-color: #303030;
    align-items: center;
    @include space_around;
    @include upbold;

    .icon {
        display: flex;
        @include upbold;

    }
}
</style>