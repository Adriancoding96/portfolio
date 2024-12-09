<script lang="ts">
  import '@fortawesome/fontawesome-free/css/all.min.css'
</script>


<h2 class="text-3xl font-bold mb-8">Projects</h2>
<div class="grid grid-cols-3 gap-6 h-80">
  <div class="card card-hover p-4 flex flex-col h-full">
    <header class="card-header">
      <h2 class="h2">Simple Repositories</h2>
    </header>
    <section class="flex-grow p-4">Full-stack git clone. Allowing users to control versions of projects, pull projects, merge projects, and collaborate on projects The back-end is built using Java Spring Boot, MySQL, and Docker. The frontend is build using Sveltekit, and Tailwindcss. The command line interface is built using Rust. This is a continous work in progress as im constantly working on new features to implement and optimize.</section>
    <footer class="card-footer space-x-4 mt-auto">
      <i class="fa-brands fa-java text-3xl"></i>
      <i class="fa-brands fa-rust text-3xl"></i>
      <i class="fa-brands fa-js text-3xl"></i>
    </footer>
  </div>
  <div class="card card-hover p-4 flex flex-col h-full">
    <header class="card-header">
      <h2 class="h2">Tree Walk Interperter</h2>
    </header>
    <section class="flex-grow p-4">Interperter built in Java, with implemeted custom lexer, scanner, syntax-tree reader. This project is created with the help of the fantastic book "Crafting Interperters" by Robert Nystrom.</section>
    <footer class="card-footer space-x-4 mt-auto">
      <i class="fa-brands fa-java text-3xl"></i>
    </footer>
  </div>
  <div class="card card-hover p-4 flex flex-col h-full">
    <header class="card-header">
      <h2 class="h2">Fuzzy File Searcher</h2>
    </header>
    <section class="flex-grow p-4">TUI application to search and navigate through unix file trees. This project was inspired by telescope in neovim to provide a lightweight alternative to be used directly in the terminal. The application is built in Rust using the Ratatui crate.</section>
    <footer class="card-footer space-x-4 mt-auto">
      <i class="fa-brands fa-rust text-3xl"></i>
    </footer>
  </div>
</div>
