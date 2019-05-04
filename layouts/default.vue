<template>
    <div>
        <v-header></v-header>
        <nuxt />
    </div>
</template>

<script>
    import VHeader from '@/components/common/header';

    export default {
        components: {
            VHeader
        },
    }
</script>

<style>
    html {
        font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
          Roboto, 'Helvetica Neue', Arial, sans-serif;
        font-size: 16px;
        word-spacing: 1px;
        -ms-text-size-adjust: 100%;
        -webkit-text-size-adjust: 100%;
        -moz-osx-font-smoothing: grayscale;
        -webkit-font-smoothing: antialiased;
        box-sizing: border-box;
    }

    *,
    *:before,
    *:after {
        box-sizing: border-box;
        margin: 0;
    }

    .container {
        box-sizing: border-box;
        margin-left: auto;
        margin-right: auto;
        max-width: 1100px;
        min-width: 320px;
    }
</style>
