<template>
    <div></div>
</template>

<script>
export default {
    name:'my-check'
}
</script>

<style scoped>
 .check{
        margin-left: 8%;
        position: absolute;
        display: block;
        align-items: center; 
    }
    .notChecked{
        width: 20px;
        height: 20px;
        margin-left: 6%;
        background-color: rgb(255, 255, 255);
        border-radius: 5px;
        cursor: pointer;
    }
    .notChecked:hover{
        background-color:rgb(184, 240, 240);
    }
    .checked{
        background-image: url(https://cdn4.iconfinder.com/data/icons/materia-flat-interface-vol-2/24/008_078_checkbox_check_box_control_checked-512.png);
        background-size: cover;
    }
</style>