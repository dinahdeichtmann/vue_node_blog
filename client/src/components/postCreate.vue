<script setup>
import { ref } from "vue";

const title = ref("");
const emit = defineEmits(["sendPost"]);

async function sendPost(event) {
  event.preventDefault();

  emit("sendPost", title.value);

  title.value = "";
}
</script>

<template>
  <head>
    <link
      rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/bootstrap@4.0.0/dist/css/bootstrap.min.css"
      integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm"
      crossorigin="anonymous"
    />
  </head>
  <body>
    <div class="postCreate">
      <h1>Create Post</h1>
      <form @submit="sendPost">
        <div class="form-group">
          <label>Title: {{ title }}</label>
          <input class="form-control" v-model="title" required />
        </div>
        <button class="btn btn-primary">Submit</button>
      </form>
    </div>
  </body>
</template>

<style></style>
