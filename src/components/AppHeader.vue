<script >
export default {
    data() {
        return {
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
    }
}
</script>
<template>
    <header>
        <div class="header_cont">
            <a href="/" class="brand">
                <img src="/img/dc-logo.png" alt="dc_logo">
            </a>
            <nav>
                <ul>
                    <li v-for="(item, index) in menu" :key="index">
                        <a :href="item.url" :class="item.active ? 'active' : ''">
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
        @include space_around;
    }

    img {
        width: 80%;
    }

    ul {
        list-style: none;
        margin: 2rem 1rem;
        @include center;

        li a {
            padding: 1em;
            font-size: 16px;
            text-decoration: none;
            transition: border 0.3s;
            @include upbold;

            &.active,
            &:hover {
                color: $primary;
                border-bottom: 2px solid $primary;
                padding-bottom: 2em;
            }
        }
    }
}
</style>