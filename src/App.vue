<template>
  <main class="app">
    <section class="greeting">
      <h2 class="title">
        What's up,
        <input type="text" placeholder="name here" v-model="name" />
      </h2>
    </section>

    <section class="create-todo">
      <h3>create a todo</h3>

      <form @submit.prevent="addTodo">
        <h4>What's on your todo list?</h4>
        <input
          type="text"
          placeholder="e.g make a video"
          v-model="input_content"
        />
        <h4>pick category</h4>
        <div class="options">
          <label>
            <input
              type="radio"
              name="category"
              id="category1"
              value="business"
              v-model="input_category"
            />
            <span class="bubble business"></span>
            <div>Business</div>
          </label>

          <label>
            <input
              type="radio"
              name="category"
              id="category1"
              value="personal"
              v-model="input_category"
            />
            <span class="bubble personal"></span>
            <div>Personal</div>
          </label>
        </div>
        <input type="submit" value="Add" />
      </form>
    </section>






  </main>
</template>

<script setup>
import { ref, onMounted, computed, watch } from "vue";
const todos = ref([]);
const name = ref([]);

const input_content = ref("");
const input_category = ref([]);

const todos_asc = computed(() =>
  todos.value.sort((a, b) => {
    return b.createdAt - a.createdAt;
  })
);
</script>

<style></style>
