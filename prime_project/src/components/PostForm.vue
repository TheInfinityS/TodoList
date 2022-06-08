<template>
    <form @submit.prevent><!--чтобы не обновлялась страница-->
        <h2><span class="Todo">Todo</span><span class="list">List</span></h2>
        <my-input
            type="text" 
            placeholder="Название" 
            v-model="post.title"
        /> 
        <my-input 
            type="text" 
            placeholder="Описание" 
            v-model="post.body"
        />
        <my-button
            class="CreateButton"
            @click="createPost"
        >   Создать
        </my-button>       
    </form>
</template>

<script>
    export default{
        data(){
            return{
                post:{
                    title:'',
                    body:'',
                }
            }
        },
        methods:{
            createPost(){
                this.post.id=Date.now();
                this.post.checkbox=false;
                this.$emit('create',this.post)
                this.post={
                    title:'',
                    body:'',
                }
            }
        }
    }
</script>

<style scoped>
    h2{
        text-align: center;
        font-size:50px;
    }
    .Todo{
        color:rgb(29, 185, 178);
    }
    .list{
        color:rgb(52, 28, 139)
    }
</style>
