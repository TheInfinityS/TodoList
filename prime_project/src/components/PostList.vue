<template>
    <div v-if="posts.length>0">
        <transition-group name="todo-list">
            <post-item
                v-for="post in posts" 
                :post="post"
                :key="post.id"
                @remove="$emit('remove',post)"
                @edit="$emit('edit',post)"
                @check="$emit('check',post)"
            />
        </transition-group>
    </div>
    <h3 v-else>Список дел пуст</h3>
</template>

<script>
import PostItem from "@/components/PostItem";
    export default {
        components:{PostItem},
        props:{
            posts:{
                type:Array,
                required:true,
            }
        }
    }
</script>


<style scoped>
h3{
    text-align: center;
    font-size:20px;
    color:rgb(255, 255, 255)
}
.todo-list-item {
  display: inline-block;
  margin-right: 10px;
}
.todo-list-enter-active,
.todo-list-leave-active {
  transition: all .4s ease;
}
.todo-list-enter-from,
.todo-list-leave-to {
  opacity: 0;
  transform: translateY(30px);
}
</style>