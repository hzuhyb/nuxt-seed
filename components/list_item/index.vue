<template>
    <div>
        <div class="item" v-for="item in projects">
            <div class="item_user">
                <div class="time">{{ item.join_time }}</div>
            </div>
            <div class="user_opinion">{{ item.opinion }}</div>
            <div class="item_inner" v-bind:class="{ islink: item.type === 'link' }">
                <div class="item_info">
                    <div class="item_header">
                        <nuxt-link class="link" to="/detail">
                            <h2 class="info_title">{{ item.name }}</h2>
                        </nuxt-link>
                    </div>
                    <nuxt-link to="/detail">
                        <p class="item_intro">{{ item.intro }}</p>
                    </nuxt-link> 
                </div>
                <nuxt-link class="item_link" to="/detail">
                    <img class="item_icon" :src="item.avatar_path + '?imageView2/0/w/160/h/160'" alt="" 
                        v-if="item.type !== 'link'">
                    <img class="item_icon" :src="item.avatar_path" alt="" v-else>
                </nuxt-link>
            </div>
            <div class="btn_controls">
                <div class="btn btn_income">
                    <i class="icon income_icon"></i>
                    <span class="income_txt">{{ item.tokens_got }}</span>
                </div>
                <a class="btn btn_like" :rel="item.liked ? 'unlike' : 'like'"
                    v-bind:class="{ active: item.liked }">
                    <i class="icon heart_icon"></i>
                    <span class="btn_txt btn_like_txt">
                        {{ item.thumbup_count }}
                    </span>
                </a>
                <a class="btn btn_comment">
                    <i class="icon comment_icon"></i>
                    <span class="btn_txt">{{ item.comment_count }}</span>
                </a>
                <ul class="tag">
                    <li class="tag_item">
                        {{ item.tags[0] }}
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            projects: {
                type: Array,
                required: true
            }
        },
        data () {
            return {
                
            }
        },
        mounted () {
            
        }
    }
</script>

<style lang="less">
    .item {
        margin-bottom: 10px;
        padding: 20px;
        background-color: #fff;
        border: 1px solid #f3f3f3;
        border-radius: 4px;
    }
    .item_user {
        margin-bottom: 5px;
        display: flex;
        flex-direction: row;
        align-items: center;
        .user_info {
            display: flex;
            flex-direction: row;
            align-items: center;
            &:hover > .info_name {
                color: #443f54;
            }
        }
        .vip_type_icon {
            margin-left: 5px;
            width: 14px;
            height: 14px;
        }
        .info_avatar {
            margin-right: 5px;
            width: 20px;
            height: 20px;
            border-radius: 50%;
        }
        .info_name {
            line-height: 14px;
        }
        .time {
            margin-left: 8px;
            font-size: 13px;
        }
    }
    .user_opinion {
        text-align: left;
    }
    .item_inner {
        display: flex;
        flex-direction: row;
        align-items: flex-start;
        &.islink {
            margin-top: 10px;
            background-color: #F4F4F4;
            border-radius: 4px;
            padding: 10px;
            border: 1px solid #eee;
            .tag_item {
                background-color: #fff;
            }
        }
    }
    .hot_list {
        border-radius: 4px;
        background-color: #fff;
        border: 1px solid #f3f3f3;
    }
    .hot_item {
        margin-bottom: 0px;
        padding: 20px;
        border: none;
        border-bottom: 1px solid #f3f3f3;
        border-radius: 0;
        background-color: transparent;
    }
    .item_link {
        display: inline-block;
        margin-left: 10px;
        width: 80px;
        height: 80px;
    }
    .item_icon {
        display: block;
        width: 80px;
        height: 80px;
        border-radius: 4px;
        object-fit: contain;
    }
    .item_info {
        display: inline-block;
        text-align: left;
        overflow: hidden;
        flex: 1;
    }
    .item_header {
        display: flex;
        flex-direction: row;
        align-items: center;
    }
    .link {
        margin-right: 15px;
        overflow: hidden;
    }
    .info_title {
        font-size: 18px;
        font-weight: 500;
        text-overflow: ellipsis;
        white-space: nowrap;
        width: 100%;
        overflow: hidden;
    }
    .item_intro {
        margin: 5px 0 0;
    }
    .btn_controls {
        margin-top: 10px;
        display: flex;
        flex-direction: row;
        align-items: center;
        .btn {
            height: 22px;
            padding: 0 10px;
            vertical-align: top;
            border-radius: 3px;
            display: flex;
            flex-direction: row;
            align-items: center;
            &:first-child {
                padding-left: 0;
            }
        }
        .btn_like {
            border-color: #e8e8e8;
            color: #999;
            background: #fff;
            fill: #999;
            &:hover > .heart_icon {
                // background: url(./images/like_hover.png);
                background-size: 100%;
            }
            &.active {
                .heart_icon {
                    // background: url(./images/like_active.png);
                    background-size: 100%;
                }
            }
        }
        .btn_income {
            display: flex;
            align-items: center;
        }
        .btn_comment {
            &:hover > .comment_icon {
                // background: url(./images/comment_hover.png);
                background-size: 100%;
            }
        }
        .btn_txt, .income_txt {
            font-size: 14px;
        }
        .icon {
            display: inline-block;
            margin-right: 5px;
            background-repeat: no-repeat;
            width: 14px;
            height: 14px;
        }
        .income_icon {
            // background: url(./images/income.png);
            background-size: 100%;
        }
        .heart_icon {
            // background: url(./images/like.png);
            background-size: 100%;
        }
        .comment_icon {
            // background: url(./images/comment.png);
            background-size: 100%;
        }
        .tag {
            margin-left: 10px;
        }
    }
</style>