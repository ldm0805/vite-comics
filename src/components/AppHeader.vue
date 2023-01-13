<script >
export default {
    data() {
        return {
            activeItem: 0,
            menu: [
                {
                    label: 'Characters',
                    url: '#',
                    active: false
                },
                {
                    label: 'Comics',
                    url: '#',
                    active: true
                },
                {
                    label: 'Movies',
                    url: '#',
                    active: false
                },
                {
                    label: 'Tv',
                    url: '#',
                    active: false
                },
                {
                    label: 'Games',
                    url: '#',
                    active: false
                },
                {
                    label: 'Collectibles',
                    url: '#',
                    active: false
                },
                {
                    label: 'Videos',
                    url: '#',
                    active: false
                },
                {
                    label: 'Fans',
                    url: '#',
                    active: false
                },
                {
                    label: 'News',
                    url: '#',
                    active: false
                },
                {
                    label: 'Shop',
                    url: '#',
                    active: false
                }
            ]
        }
    },
    methods: {
        selectedItem(index) {
            this.activeItem = index
        },
    }
}
</script>
<!-- Header -->
<template>

    <header class="container">
        <!-- Logo header -->
        <div class="header_cont">
            <a href="/" class="brand">
                <img src="/img/dc-logo.png" alt="dc_logo">
            </a>
        </div>
        <!-- Navbar -->
        <nav class="nav_cont">
            <ul>
                <!-- For per la navbar + click sugli elementi per assegnare la classe active -->
                <li v-for="(item, index) in menu" :key="index" @click="selectedItem(index)"
                    :class="(activeItem === index) ? 'active' : ''">
                    <a :href="item.url">
                        {{ item.label }}
                    </a>
                </li>
            </ul>
        </nav>
    </header>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;


.container {

    @include justify_content_between;
    margin-top: 1em;
    text-align: center;

    ul {
        margin: 2rem 1rem;
        @include center;

        .active {
            color: $primary;
            border-bottom: 3px solid $primary;
            padding-bottom: 2em;
        }

        li a {
            padding: 1em;
            font-size: 16px;
            text-decoration: none;
            transition: border 0.3s;
            @include upbold;

        }
    }
}
</style>