<script >
export default {
    data() {
        return {
            // Array di oggetti icone footer
            icon: [
                {
                    label: 'buy-comics-digital-comics.png',
                    description: 'DIGITAL COMICS'
                },
                {
                    label: 'buy-comics-merchandise.png',
                    description: 'DC MERCHANDISE'
                },
                {
                    label: 'buy-comics-subscriptions.png',
                    description: 'SUBSCRIPTION'
                },
                {
                    label: 'buy-comics-shop-locator.png',
                    description: 'COMIC SHOP LOCATOR'
                },
                {
                    label: 'buy-dc-power-visa.svg',
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
    // Funzione per visualizzare prime icone nel footer;
    methods: {
        getImagePath: function (img) {
            return `/img/${img}`
        }
    }
};
</script>

<template>
    <footer class="container">
        <div class="footer_cont">
            <ul>
                <!-- Ciclo for per ciclare le prime icone del footer -->
                <li v-for="(object, index) in icon" :key="index">
                    <a class="link-flex" href="#">
                        <img :src="getImagePath(object.label)" alt="logo">
                        <span class="description">{{ object.description }}</span>
                    </a>
                </li>
            </ul>
        </div>
        <!-- Footer links -->
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
                <!-- Link footer -->
                <div class="footer-links">
                    <h4>Shop</h4>
                    <ul>
                        <li><a href="#">Shop DC</a></li>
                        <li><a href="#">Shop DC Collectibles</a></li>
                    </ul>
                </div>
            </div>
            <!-- Link footer -->
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
                <div class="img_dc_bg">
                </div>
            </div>

        </div>

        <!-- Icone social nel footer -->

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

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;


// Footer delle liste
.footer_cont {
    padding: 2em 5em;
    background-color: #0282f9;
    width: 100%;

    .contet_title {
        color: white;
        @include upbold;
    }

    .link-flex {
        display: flex;
        align-items: center;
    }

    ul {
        width: 100%;
        display: flex;
        justify-content: space-between;
        align-items: center;


        li a {
            color: $gray;
        }

        .description {
            padding-left: 1em;
        }

        img {
            width: 60px;
            height: 60px;
            object-fit: contain;
        }

        span {
            color: white;
            font-size: 10px;
        }
    }

}

// Footer delle liste




.cont_list {
    background-image: url('/img/footer-bg.jpg');
    background-size: cover;
    display: flex;
    justify-content: space-around;
    color: $white;

    .footer-links {
        padding: 2em 0em;
    }

    .dc_bg {
        background-image: url(/img/dc-logo-bg.png);
        background-size: cover;
        background-position: right center;
        width: 600px;
    }


    div {
        padding: 0em 2em;
    }

    li {
        color: $white;
        list-style: $listnone;
    }

    li a {
        color: $gray;

        &:hover {
            color: white;
        }
    }
}

.button {
    padding: 2em;
    background-color: #303030;
    @include justify_content_between;

}

.footer-button {
    @include button;

    &:hover {
        font-size: 15px;
        cursor: pointer;
        filter: brightness(1.2);
    }

}

//Liste icone social

.social {
    height: 150px;
    background-color: #303030;
    align-items: center;
    display: flex;
    justify-content: space-around;
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

            &:hover {
                filter: brightness(100);
            }
        }

        .follow {
            @include upbold;
            color: #0282f9;
            padding-right: .5em;
        }

    }
}
</style>