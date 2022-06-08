<template>
<div class="p">
    <my-check :class="{checked:post.checkBox===true}" class="notChecked" @click="$emit('check',post)"/>
    <div class="post">
        <div>
            <div><strong>Название:</strong>{{post.title}} </div>
            <div><strong>Описание:</strong>{{post.body}} </div>
        </div>
        <div>
            <my-button
                class="RemoveButton"
                @click="$emit('remove',post)"
            >Удалить</my-button>
            <my-button 
                class="EditButton"
                @click="$emit('edit',post)"
            >Изменить</my-button>
        </div>
    </div>
</div>
</template>

<script>
    export default {
        props:{
            post:{
                type:Object,
                required:true,
            }
        },
        data(){
            return{
            }
        }
    }
</script>

<style scoped>
    .p{
        display:flex;
        align-items: center;
    }
    .post{
        width: 80%;
        margin: 8px;
        font-size:20px;
        border: 1px solid rgb(50,20,120);
        display:flex;
        justify-content: space-between;
        align-items: center;  
    }
    
</style>
