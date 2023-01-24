<script setup>
  import FooterComponent from "./components/FooterComponent.vue";
  import HearderComponent from "./components/HearderComponent.vue";
  import CardComponent from "./components/CardComponent.vue";
import { ref } from "vue";
import FormPostComponent from "./components/FormPostComponent.vue";

  const posts = ref([
    {
      id:1,
      title: "Mon cours",
      text:"Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum error eius nam eveniet, voluptate repudiandae possimus assumenda. Esse magnam, accusamus illum, neque repellendus iste explicabo, doloribus similique facilis cum molestiae."
    },
    {
      id:2,
      title: "Chat GPT",
      text:"Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum error eius nam eveniet, voluptate repudiandae possimus assumenda. Esse magnam, accusamus illum, neque repellendus iste explicabo, doloribus similique facilis cum molestiae."
    },
    {
      id:3,
      title: "Cours vuejs",
      text:"Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum error eius nam eveniet, voluptate repudiandae possimus assumenda. Esse magnam, accusamus illum, neque repellendus iste explicabo, doloribus similique facilis cum molestiae."
    },
    {
      id:4,
      title: "Symfony 6",
      text:"Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum error eius nam eveniet, voluptate repudiandae possimus assumenda. Esse magnam, accusamus illum, neque repellendus iste explicabo, doloribus similique facilis cum molestiae."
    },
    {
      id:5,
      title: "C#",
      text:"Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum error eius nam eveniet, voluptate repudiandae possimus assumenda. Esse magnam, accusamus illum, neque repellendus iste explicabo, doloribus similique facilis cum molestiae."
    },
    {
      id:6,
      title: "Nodejs",
      text:"Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum error eius nam eveniet, voluptate repudiandae possimus assumenda. Esse magnam, accusamus illum, neque repellendus iste explicabo, doloribus similique facilis cum molestiae."
    },
    {
      id:7,
      title: "Java",
      text:"Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum error eius nam eveniet, voluptate repudiandae possimus assumenda. Esse magnam, accusamus illum, neque repellendus iste explicabo, doloribus similique facilis cum molestiae."
    },
    {
      id:8,
      title: "Python",
      text:"Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum error eius nam eveniet, voluptate repudiandae possimus assumenda. Esse magnam, accusamus illum, neque repellendus iste explicabo, doloribus similique facilis cum molestiae."
    }
  ])



</script>

<template>
  <header>
    <HearderComponent />
  </header>

  <main>
    
    <div class="mt-4 p-5 bg-primary text-white rounded">
      <h1>Bienvenu dans mon blog</h1>
      <p>Lorem ipsum...</p>
    </div>
    <div class="row justify-content-center">
      <div class="col-6 ">
        <FormPostComponent :posts="posts" />
      </div>
    </div>
    <section class="mt-3">
      <div class="row">
        <div class="col-4" v-for="post in posts" :key="post.id">
          <CardComponent :post="post" :posts="posts"/>
        </div>

      </div>
      
    </section>
  </main>
  <FooterComponent />
</template>

<style scoped>

</style>
