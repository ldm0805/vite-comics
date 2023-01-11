<script >
export default {
}
</script>

<template>
    <div class="content_cont">
        <div class="contet_title"> .. coming soon</div>
    </div>
</template>

<style lang="scss">
@use '../styles/partials/mixins' as *;

.content_cont {
    height: 100px;
    background-color: rgb(88, 88, 88);
    display: flex;
    align-items: center;

    .contet_title {
        color: white;
        @include upbold;
    }
}
</style>