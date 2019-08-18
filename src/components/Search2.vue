<template>
    <div class="header-container" v-bind:class="{ products: tab === 'products' }">
        <div>
            <div class="logo">
                <img src="/assets/logo.svg" height="46" />
            </div>
            <div class="search">
                <div class="search-input">
                    <input type="text" placeholder="Leitin að Villa..." />
                </div>
                <div class="search-tabs">
                    <a href="#" role="tab" v-bind:class="{ active: tab === 'info' }" v-on:click="setTab('info')">
                        <span>Upplýsingar<span>24</span></span>
                    </a>
                    <a href="#" role="tab" class="product-tab" v-bind:class="{ active: tab === 'products' }" v-on:click="setTab('products')">
                        <span><div class="new products-attention"></div>Vöruleit<span>62</span></span>
                    </a>
                </div>
            </div>
            <div class="menu">
                <img src="/assets/ICELAND.svg" height="22" />
                <img src="/assets/user.svg" height="24" />
                <img src="/assets/menu.svg" height="16" />
            </div>
        </div>
    </div>
</template>

<script lang="ts">
    export default {
        data() {
            return {
                tab: 'info',
            };
        },
        methods: {
            setTab(which: 'info' | 'products') {
                this.tab = which;
            }
        }
    }
</script>

<style lang="scss" scoped>
    .header-container {
        padding: 24px 0 0 0;
        background: #fff;
        display: flex;
        align-items: center;
        justify-content: center;
        border-bottom: 2px solid #464646;

        &.products {
            border-bottom-color: #FFBA00;
        }

        > div {
            display: flex;
        }
    }

    .search {
        width: 600px;
        margin-right: 100px;
        margin-left: 16px;

        .search-input {
            width: 100%;
            height: 46px;

            input {
                border-radius: 24px;
                width: 100%;
                height: 100%;
                outline: 0;
                border: 1px solid #e5e5e5;
                padding: 0 24px;
                font-size: 18px;
                transition: all .2s linear;
                box-shadow: 0 0 0 rgba(0,0,0,0);

                &:hover {
                    border-color: darken(#e5e5e5, 5%);
                }

                &:focus {
                    box-shadow: 0 3px 30px rgba(0,0,0,.2);
                }
            }

        }

        .search-tabs {
            display: flex;
            margin-top: 16px;

            > a {
                font-size: 13px;
                font-weight: 500;
                text-decoration: none;
                color: #464646;
                display: flex;
                margin-right: 16px;
                align-items: center;
                padding: 12px 24px;
                border: 1px solid #e5e5e5;
                border-bottom: none;
                border-radius: 8px 8px 0 0;

                > div {
                    background: #eee;
                    width: 24px;
                    height: 24px;
                    border-radius: 50%;
                    display: flex;
                    justify-content: center;
                    align-items: center;
                    margin-right: 8px;

                    &.info {
                        background: #464646;
                    }

                    &.products {
                        background-color: #FFBA00;
                    }
                }

                > span {
                    color: inherit;
                    transition: color .2s linear;

                    > .new {
                        text-transform: uppercase;
                        background: #FFBA00;
                        width: 8px;
                        height: 8px;
                        font-weight: 600;
                        margin-right: 16px;
                        margin-left: -8px;
                        display: inline-block;
                        border-radius: 4px;
                        position: relative;
                        top: -1px;
                        border: 1px solid transparent;
                    }

                    > span {
                        display: inline-block;
                        margin-left: 8px;
                        opacity: .4;
                    }
                }

                &:hover {
                    > span {
                        color: lighten(#464646, 10%);
                        text-decoration: underline;
                    }
                }

                &.active {
                    border-color: #464646;
                    background-color: #464646;

                    .products-attention {
                        animation: attentionWhite 3s infinite !important;
                    }

                    &.product-tab {
                        border-color: #FFBA00;
                        background-color: #FFBA00;
                    }

                    span {
                        color: #fff;
                        text-decoration: none;

                        > .new {
                            border-color: #fff;
                        }
                    }
                }
            }
        }
    }

    .menu {
        display: flex;
        height: 46px;
        align-items: center;

        > img:not(:first-child) {
            margin-left: 24px;
        }

        img {
            transition: all .2s linear;
            transform: translate3d(0,0,0);
            cursor: pointer;
            &:hover {
                opacity: .7;
            }
        }
    }

    .products-attention {
        animation: attention 3s infinite;
    }

    @keyframes attention {
        0% {
            box-shadow: 0 0 0 0 rgba(255,186,0, 0.4);
        }
        70% {
            box-shadow: 0 0 0 10px rgba(255,186,0, 0);
        }
        100% {
            box-shadow: 0 0 0 0 rgba(255,186,0, 0);
        }
    }

    @keyframes attentionWhite {
        0% {
            box-shadow: 0 0 0 0 rgba(255,255,255, 0.4);
        }
        70% {
            box-shadow: 0 0 0 10px rgba(255,255,255, 0);
        }
        100% {
            box-shadow: 0 0 0 0 rgba(255,255,255, 0);
        }
    }
</style>