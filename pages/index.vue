<template>
    <section class="container wrap">
        <div>
            <list-item :projects="projects"></list-item>
        </div>
    </section>
</template>

<script>
    import Logo from '~/components/Logo.vue'
    import ListItem from '~/components/list_item/index.vue'
    import Request from '@/service'

    export default {
        data () {
            return {
                projects: []
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
            if (process.server) {
                console.log('asyncdata')
                let params = {
                    locale: "cn",
                    start_num: 0,
                    page_size: 15,
                    tag_name: "latest"
                };
                let result = await Request.post('/v1/product/listproducts',  params);
                return { projects: result.data }
            }
        },
        async fetch ({ store }) {
            console.log('fetch')
            
        },
        mounted () {
            console.log('mounted')
        },
        methods: {

        },
        components: {
            Logo,
            ListItem
        }
    }
</script>

<style>
    .wrap {
        margin-top: 80px;
    }
</style>