<template>
    <div>
        <post-form
            @create="createPost"
        />
        <my-dialog v-model:show="dialogVisible">
           <my-input
                type="text" 
                placeholder="Название" 
                v-model="title"
           />
           <my-input
                type="text" 
                placeholder="Название"
                v-model="body"
           />
           <my-button
                class="ChangeEditButton"
                @click="saveUpdate"
                >Сохранить изменения</my-button>
        </my-dialog>
        <post-list 
            :posts="posts"
            @remove="removePost"
            @edit="editPost"
            @check="checkPost"
        /><!--связали с постами-->
    </div>
</template>

<script>
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";
    export default{
        components:{
            PostForm, PostList
        },
        data(){
            return{
                posts:[
                    {id:1, title:'One', body:'Odin',checkBox:false},
                    {id:2, title:'Two', body:'Dva',checkBox:false},
                    {id:3, title:'Three', body:'Tri',checkBox:false},
                    {id:4,title:'Four', body:'Chetiry',checkBox:false},
                ],
                dialogVisible:false,
                body:"qwe",
                title:"qwe",
                id:99,
            }
        },
        methods:{
            createPost(post){
                this.posts.push(post);
            },
            removePost(post){
                this.posts=this.posts.filter(p=>p.id !==post.id);
            },
            editPost(post){
                this.dialogVisible=true;
                this.title=this.posts.find(p=>p.id==post.id).title;
                this.body=this.posts.find(p=>p.id==post.id).body;
                this.id=this.posts.find(p=>p.id==post.id).id;
                console.log(title);
            },
            saveUpdate(){
                this.posts.find(p=>p.id==this.id).title=this.title;
                this.posts.find(p=>p.id==this.id).body=this.body;
                this.dialogVisible=false;
            },
            checkPost(post){
                post.checkBox=!post.checkBox;
            }
        }
    }
</script>

<style>
    body{
        background-color:black;
        color:white ;
        background-size:cover;
        background-image: url(https://kartinkin.net/uploads/posts/2021-07/thumbs/1627207938_24-kartinkin-com-p-krasivii-tyomnii-fon-gorizontalnii-krasivo-24.jpg);
    }
</style>