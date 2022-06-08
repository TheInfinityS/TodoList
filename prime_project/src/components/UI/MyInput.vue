<template>
    <input 
        :value="modelValue" 
        @input="updateInput" 
        class="input" 
        type="text"
    >
</template>

<script>
export default {
    name:"my-input",
    props:{
        modelValue:[String, Number]
    },
    methods:{
        updateInput(event){
            this.$emit('update:modelValue',event.target.value)
        }
    }
}
</script>

<style scoped>
    .input{
        background-color:rgb(50,20,120);
        border:none;
        margin:2px;
        color:white;
        width:60%;
        height:30px;
        font-size:100%;
        border-radius:10px; 
        text-align: center;
        margin-left: 20%;    
    }
</style>