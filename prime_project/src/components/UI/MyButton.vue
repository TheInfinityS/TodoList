<template>
    <button>
        <slot></slot>
    </button>
</template>

<script>
export default {
    name:'my-button'
}
</script>

<style scoped>
    button{
        cursor: pointer;
        color:rgb(255, 255, 255);
        border:none;
    }
    .CreateButton{
        background-color: rgb(9, 112, 107);
        border-radius: 10px;
        height: 30px;
        margin-left: 75%;
        font-size:100%;
    }
    .RemoveButton{
        background-color: rgb(91, 9, 112);
        margin: 2px;
    }
    .EditButton{
        margin:2px;
        background-color: rgb(9, 24, 112);
    }
    .ChangeEditButton{
        margin-left:50%;
        border-radius: 12px;
        padding: 20px;
        background-color: rgb(9, 112, 107);
    }
</style>