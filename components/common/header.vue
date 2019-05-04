<template>
    <div class="header">
        <div class="container header-inner">
            <nuxt-link class="link-logo" to="/">
                <img src="@/assets/images/common/logo.png" alt="">
            </nuxt-link>
            <div class="search-wrap">
                <Input icon="ios-search" placeholder="搜索" style="width: 300px"></Input>
            </div>
            <!-- <div class="actions-wrap">
                <nuxt-link class="link-download" to="/download">
                    <img src="@/assets/images/common/app.png" alt="">
                    <span class="download-txt">下载APP</span>
                </nuxt-link>
                <div class="login-buttons">
                    <a class="button button_primary login_button" href="javascript:;">
                        <span>登录</span>
                    </a>
                    <a class="button button_default sign_button" href="javascript:;">
                        <span class="">注册</span>
                    </a>
                </div>
            </div> -->
        </div>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="less">
    .header {
        position: fixed;
        top: 0rem;
        width: 100%;
        height: 52px;
        background: #fff;
        border-bottom: 1px solid #e8e8e8;
        z-index: 1000;
    }
    .header-inner {
        display: flex;
        align-items: center;
        padding: 20px;
        padding-bottom: 10px;
        padding-top: 10px;
    }
    .link-logo {
        display: inline-flex;
        flex-direction: row;
        align-items: center;
        margin: 0 20px 0 0;
        img {
            width: 97px;
            height: 27px;
            object-fit: contain;
        }
    }
</style>