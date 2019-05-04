<template>
    <section class="wrap">
        <div>
            <logo />
            <h1 class="title">
                home page
            </h1>
            <h2 class="subtitle" >
                <nuxt-link to="/detail">go detail page</nuxt-link>
            </h2>
        </div>
    </section>
</template>

<script>
    import Logo from '~/components/Logo.vue'
    import Request from '@/service'

    export default {
        data () {
            return {
                
            }
        },
        head () {
            return {
                title: '首页',
                meta: [
                    { hid: 'home custom title', name: 'home', content: 'home custom title description' }
                ]
            }
        },
        async asyncData ({ store, error }) {
            console.log('asyncdata')
            let params = {
                locale: "cn",
                start_num: 0,
                page_size: 15,
                tag_name: "latest"
            };
            let result = await Request.post('/v1/product/listproducts',  params);
        },
        async fetch ({ store, params }) {
            console.log('fetch')
        },
        mounted () {
            console.log('mounted')
        },
        methods: {

        },
        components: {
            Logo
        }
    }
</script>

<style>
    .wrap {
        margin: 0 auto;
        min-height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
    }
    .title {
        font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
          'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
        display: block;
        font-weight: 300;
        font-size: 100px;
        color: #35495e;
        letter-spacing: 1px;
    }
    .subtitle {
        font-weight: 300;
        font-size: 42px;
        color: #526488;
        word-spacing: 5px;
        padding-bottom: 15px;
    }
    .links {
        padding-top: 15px;
    }
</style>