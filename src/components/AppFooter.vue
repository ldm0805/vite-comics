<script >
export default {
    data() {
        return {
            icon: [
                {
                    label: 'buy-comics-digital-comics.png',
                    active: false,
                    description: 'DIGITAL COMICS'
                },
                {
                    label: 'buy-comics-merchandise.png',
                    active: true,
                    description: 'DC MERCHANDISE'
                },
                {
                    label: 'buy-comics-subscriptions.png',
                    active: false,
                    description: 'SUBSCRIPTION'
                },
                {
                    label: 'buy-comics-shop-locator.png',
                    active: false,
                    description: 'COMIC SHOP LOCATOR'
                },
                {
                    label: 'buy-dc-power-visa.svg',
                    active: false,
                    description: 'DC POWER VISA'
                },
            ],
            social: [
                {
                    logo: 'footer-facebook.png',
                },
                {
                    logo: 'footer-periscope.png',
                },
                {
                    logo: 'footer-pinterest.png',
                },
                {
                    logo: 'footer-twitter.png',

                },
                {
                    logo: 'footer-youtube.png',
                },
            ]
        }
    },
    methods: {
        getImagePath: function (img) {
            return `/img/${img}`
        }
    }
};
</script>

<template>
    <footer>
        <div class="footer_cont">
            <ul>
                <li v-for="(object, index) in icon" :key="index">
                    <img :src="getImagePath(object.label)" alt="loghi">
                    <span class="description">{{ object.description }}</span>
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
                <button class="footer-button">Sign-up now!</button>
            </div>
            <div class="icon">
                <h3 class="follow">Follow us</h3>
                <ul>
                    <li v-for="(object, index) in social" :key="index">
                        <a href="#"><img :src="getImagePath(object.logo)" alt="loghi"></a>
                    </li>
                </ul>
            </div>
        </div>
    </footer>
</template>

<style lang="scss">
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;



.footer_cont {

    padding: 2em;
    background-color: #0282f9;
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;

    .contet_title {
        color: white;
        @include upbold;
    }

    ul {
        width: 100%;
        justify-content: space-between;
        display: flex;
        align-items: center;
        list-style: none;

        li {
            display: flex;
            align-items: center;
        }

        .description {
            padding-left: 2em;
        }

        img {
            width: 20%;
        }

        span {
            color: white;
            font-size: 10px;
        }
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

.button {
    background-color: #303030;
    display: flex;
    justify-content: space-between;

}

.footer-button {
    @include button;

}

.social {
    height: 100px;
    background-color: #303030;
    align-items: center;
    display: flex;
    justify-content: space-between;
    @include upbold;

    .icon {
        display: flex;
        align-items: center;
        @include upbold;

        ul {
            display: flex;
            gap: .5em;

        }

        li {
            display: flex;
            color: $white;
            list-style: $listnone;
        }

        .follow {
            @include upbold;
            color: #0282f9;
            padding-right: .5em;
        }
    }
}
</style>