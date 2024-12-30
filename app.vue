<template>
      <div :class="{ 'dark-mode': isDarkMode }">
        <header>
          <h1>Flow</h1>
          <nav>
            <ul>
              <li><a href="#">Home</a></li>
              <li><a href="#">Profile</a></li>
              <li><a href="#">Messages</a></li>
              <li><a href="#">Notifications</a></li>
            </ul>
          </nav>
          <button @click="toggleDarkMode">Toggle Dark Mode</button>
        </header>
        <main>
          <NuxtPage />
        </main>
      </div>
    </template>

    <script setup>
      import { ref } from 'vue';

      const isDarkMode = ref(false);

      function toggleDarkMode() {
        isDarkMode.value = !isDarkMode.value;
      }
    </script>

    <style>
      header {
        background-color: #f8f9fa;
        padding: 20px;
        border-bottom: 1px solid #ddd;
        display: flex;
        justify-content: space-between;
        align-items: center;
      }

      header h1 {
        margin: 0;
      }

      nav ul {
        list-style: none;
        padding: 0;
      }

      nav ul li {
        display: inline;
        margin-right: 10px;
      }

      nav ul li a {
        text-decoration: none;
        color: #333;
      }

      main {
        padding: 20px;
      }

      .dark-mode {
        background-color: #333;
        color: #fff;
      }

      .dark-mode header {
        background-color: #444;
        border-bottom: 1px solid #555;
      }

      .dark-mode nav ul li a {
        color: #fff;
      }
    </style>
