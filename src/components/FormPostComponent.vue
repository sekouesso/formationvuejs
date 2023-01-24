<script setup>
import { ref } from 'vue';

const title = ref("Titre par défaut")
const text = ref("Text par défaut")
const post = ref({
    id: 0,
    title: "title",
    text: "text",
})
const props = defineProps(['posts'])
let index = ref(0);
function onSubmit(){
    if(props.posts.length===0){
        index = 1;
    }else{

        index = props.posts[props.posts.length - 1].id+1;
    }
    console.log(props.posts);
    post.value.id = index;
    //  post.value.id = Math.floor(Math.random()*100) +9
    console.log(post.value);
    // console.log(post.value.id);
    props.posts.push(post.value)
    console.log(props.posts);
    post.value = {}
    //  console.log(posts.value)
}
</script>

<template>
    <div>
        <p>Titre: {{ title }}</p>
        <p>Text: {{ text }}</p>
        <p>Post: {{ post }}</p>

        <!-- Button to Open the Modal -->
        <button type="button" class="btn btn-success float-end" data-bs-toggle="modal" data-bs-target="#myModal">
            Ajouter un Post
        </button>

        <!-- The Modal -->
        <div class="modal" id="myModal">
            <div class="modal-dialog">
                <div class="modal-content">

                    <!-- Modal Header -->
                    <div class="modal-header">
                        <h4 class="modal-title">Ajout Post</h4>
                        <button type="button" class="btn-close" data-bs-dismiss="modal"></button>
                    </div>

                    <!-- Modal body -->
                    <div class="modal-body">
                        <form @submit.prevent="onSubmit">
                            <div class="mb-3 mt-3">
                                <label for="title" class="form-label">Title:</label>
                                <input v-model="post.title" type="text" class="form-control" id="title"
                                    placeholder="Enter title" name="title">
                            </div>
                            <div class="mb-3">
                                <label for="text" class="form-label">Texte du post:</label>
                                <textarea v-model="post.text" class="form-control" id="text" placeholder="Enter text"
                                    name="text"></textarea>
                            </div>
                            
                            <div class="modal-footer">
                                <button type="submit" class="btn btn-primary" data-bs-dismiss="modal">Soumettre</button>
                                <button type="button" class="btn btn-danger" data-bs-dismiss="modal">Close</button>
                            </div>
                        </form>
                    </div>

                </div>
            </div>
        </div>
    </div>
</template>

<style>

</style>