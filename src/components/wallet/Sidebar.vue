<template>
    <div class="wallet_sidebar">
        <div class="stick">
            <div class="brand">
                <img v-if="$root.theme==='day'" src="@/assets/wallet_logo.svg" />
                <img v-else src="@/assets/wallet_logo_dark.svg" />
            </div>
            <div class="links">
                <router-link to="/wallet">
                    <img v-if="$root.theme==='day'" src="@/assets/sidebar/portfolio_nav.png" />
                    <img v-else src="@/assets/sidebar/portfolio_nav_night.png" />
                    Portfolio
                </router-link>
                <router-link to="/wallet/keys" data-cy="wallet_manage">
                    <img v-if="$root.theme==='day'" src="@/assets/sidebar/manage_nav.png" />
                    <img v-else src="@/assets/sidebar/manage_nav_night.svg" />
                    Manage
                </router-link>
                <router-link to="/wallet/transfer" data-cy="wallet_transfer">
                    <img v-if="$root.theme==='day'" src="@/assets/sidebar/transfer_nav.png" />
                    <img v-else src="@/assets/sidebar/transfer_nav_night.svg" />
                    Send
                </router-link>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
    }
</script>
<style lang="scss" scoped>
@use "../../main";

.wallet_sidebar {
    position: relative;

    .stick{
        position: sticky;
        top: 0;
    }
    .alert_icon{
        color: #f00;
        flex-grow: 1;
        justify-content: flex-end;
    }

    .brand {
        height: 150px;
        display: flex;
        justify-content: center;
        align-items: center;

        img {
            width: 80%;
            object-fit: contain;
        }
    }

    .links {
        padding: 0 !important;
        display: flex;
        flex-direction: column;

        a {
            display: flex;
            align-items: center;
            padding: 14px 24px;
            white-space: nowrap;
            opacity: 0.6;
            color: var(--primary-color-light);
            text-decoration: none;

            img{
                opacity: 0.5;
            }
        }

        a.router-link-exact-active {
            color: var(--primary-color) !important;
            opacity: 1;
            background-color: var(--bg-wallet);

            img{
                opacity: 1;
            }
        }

        img {
            width: 20px;
            margin-right: 15px;
            object-fit: contain;
        }
    }
}
</style>
