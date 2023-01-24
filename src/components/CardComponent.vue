<script setup>
const prop = defineProps(['post','posts'])
function deletePost(id){
  let pos = prop.posts.find(p=>p.id == id);
  console.log(pos.id);
   prop.posts.splice(pos.id, 1)
  }
</script>
<template>
     <div class="card m-2">
            <div class="card-body">
              <h4 class="card-title">{{prop.post.title}}</h4>
              <p class="card-text"> {{prop.post.text }}</p>
              <a href="#" class="btn btn-primary">Voir plus</a>
              <a :href="prop.post.id" @click.prevent="deletePost(prop.post.id)" class="btn btn-danger">supprimer</a>
            </div>
          </div>
</template>
<style scoped></style>