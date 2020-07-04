<template>
    <transition name="fade">
        <div class="update_popup" v-if="isActive">
            <div class="bg"></div>
            <div class="content">
                <img class="cover" src="@/assets/update_popups/update_bg_day.svg">
                <p class="title">AVAX Wallet is now HD</p>
                <p class="info"></p>
                <button class="ava_button" @click="confirm">Got it</button>
            </div>
        </div>
    </transition>
</template>
<script>
    const flag_title = "update_07_04_20"


    export default {
        data(){
            return {
                isActive: false,
            }
        },
        created() {

            localStorage.removeItem(flag_title);
            var isViewed = localStorage.getItem(flag_title);

            if(!isViewed){
                this.isActive = true;
            }
        },

        methods: {
            confirm(){
                this.isActive = false;
                localStorage.setItem(flag_title,"true");
            }
        }
    }
</script>
<style scoped lang="scss">
    .update_popup{
        /*width: 100%;*/
        /*height: 100%;*/
        position: fixed;
        bottom: 0px;
        right: 0px;
        z-index: 4;

    }
    .bg{
        display: none;
        position: absolute;
        width: 100%;
        height: 100%;
        background-color: rgba(0,0,0,0.05);
    }

    .content{
        background-color: #fff;
        position: absolute;
        right: 18px;
        bottom: 18px;
        /*height: 60px;*/
        width: 320px;
        z-index: 2;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        padding: 30px;
        overflow: auto;
        border-radius: 6px;
    }

    /*.cover_cont{*/
    /*    position: relative;*/
    /*    display: flex;*/
    /*    align-items: center;*/
    /*    justify-content: center;*/
    /*    overflow: auto;*/
    /*}*/

    .title{
        width: 100%;
        z-index: 2;
        color: #FFF;
        font-size: 2rem;
        position: relative;
        text-align: center;
    }
    
    .cover{
        position: absolute;
        top: 0px;
        left: 0px;
        object-fit: cover;
        width: 100%;
    }

    button{
        position: relative;
        margin: auto;
        background-color: #E84970 !important;
        color: #fff;
        margin-top: 25px;
    }
</style>