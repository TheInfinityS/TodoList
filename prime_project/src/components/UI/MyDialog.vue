<template>
    <div class="Update" v-if="show" @click.stop="hideUpdate">
        <div @click.stop class="Update_content">
            <slot></slot>
        </div>
    </div>
</template>

<script>
export default {
    name:'my-dialog',
    props:{
        show:{
            type:Boolean,
            default:false,
        }
    },
    methods:{
        hideUpdate(){
            this.$emit('update:show',false)
        }
    }
}
</script>

<style scoped>
    .Update{
        top:0;
        bottom:0;
        left: 0;
        right: 0;
        background:rgba(0,0,0,0.5);
        position:fixed;
        display: flex;
    }
    .Update_content{
        margin:auto;
        border-radius: 12px;
        padding: 20px;
        background-size: cover;
        background-image: url(https://images.wallpaperscraft.ru/image/single/fon_nebo_tochki_svet_83482_1920x1080.jpg);
    }
</style>