<template>
    <main class="main">
        <div class="container">
        <slot>
<router-view></router-view>
        </slot>
        </div>
    </main>
</template>
<script>
export default {
    name: "Main",
}
</script>
<style lang="scss">
    .main {
        padding: 20px 0;
    }
</style>