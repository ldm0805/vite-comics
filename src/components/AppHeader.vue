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
    <header>
        <!-- Logo header -->
        <div class="header_cont">
            <a href="/" class="brand">
                <img src="/img/dc-logo.png" alt="dc_logo">
            </a>
            <!-- Navbar -->
            <nav>
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
        </div>
    </header>
</template>

<style lang="scss">
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;


header {
    text-align: center;

    .header_cont {
        align-items: center;
        margin-top: 1em;
        display: flex;
        justify-content: space-between;
    }

    img {
        width: 80%;
    }

    ul {
        list-style: none;
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