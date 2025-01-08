<script lang="ts">
  import '@fortawesome/fontawesome-free/css/all.min.css'
  import JavaIcon from 'devicon/icons/java/java-original.svg';
  import SpringIcon from 'devicon/icons/spring/spring-original.svg';
  import SqlIcon from 'devicon/icons/mysql/mysql-original.svg';
  import ReactIcon from 'devicon/icons/react/react-original.svg';
  import RustIcon from 'devicon/icons/rust/rust-original.svg';
  import SvelteIcon from 'devicon/icons/svelte/svelte-original.svg';
</script>

<div class="flex justify-center text-center pb-12">
  <h1 class="h1">Projects</h1>
</div>
<div class="grid grid-cols-4 gap-6 h-80">
  <div class="card card-hover p-4 flex flex-col bg-gradient-to-br variant-gradient-tertiary-primary">
    <header class="card-header mb-12">
      <h2 class="h2">Simple Repositories</h2>
    </header>
    <section class="flex-grow p-4">Full-stack git clone. Allowing users to control versions of projects, pull projects, merge projects, and collaborate on projects The back-end is built using Java Spring Boot, MySQL, and Docker. The frontend is build using Sveltekit, and Tailwindcss. The command line interface is built using Rust. This is a continous work in progress as im constantly working on new features to implement and optimize.</section>
    <footer class="card-footer flex items-center space-x-4 mt-auto">
      <img src={JavaIcon} alt="Java Icon" class="w-8 h-8" />
      <img src={RustIcon} alt="Rust Icon" class="w-8 h-8" />
      <img src={SvelteIcon} alt="Svelte Icon" class="w-8 h-8" />
    </footer>
  </div>
  <div class="card card-hover p-4 flex flex-col bg-gradient-to-br variant-gradient-primary-secondary">
    <header class="card-header mb-12">
      <h2 class="h2">Tree Walk Interperter</h2>
    </header>
    <section class="flex-grow p-4">Interperter built in Java, with implemeted custom lexer, scanner, syntax-tree reader. This project is created with the help of the fantastic book "Crafting Interperters" by Robert Nystrom.</section>
    <footer class="card-footer flex items-center space-x-4 mt-auto">
      <img src={JavaIcon} alt="Java Icon" class="w-8 h-8" />
    </footer>
  </div>
  <div class="card card-hover p-4 flex flex-col h-full bg-gradient-to-br variant-gradient-success-error">
    <header class="card-header mb-12">
      <h2 class="h2">Fuzzy File Searcher</h2>
    </header>
    <section class="flex-grow p-4">TUI application to search and navigate through unix file trees. This project was inspired by telescope in neovim to provide a lightweight alternative to be used directly in the terminal. The application is built in Rust using the Ratatui crate.</section>
    <footer class="card-footer flex items-center space-x-4 mt-auto">
      <img src={RustIcon} alt="Rust Icon" class="w-8 h-8" />
    </footer>
  </div>
  <div class="card card-hover p-4 flex flex-col h-full bg-gradient-to-br variant-gradient-primary-tertiary">
    <header class="card-header mb-12">
      <h2 class="h2">Smart Timesheets</h2>
    </header>
    <section class="flex-grow p-4">Full-stack application for automating and managing employee timesheets and types of work performed. The application uses an back-end developed using Java Spring Boot, and an front-end built using React.</section>
    <footer class="card-footer flex items-center space-x-4 mt-auto">
      <img src={JavaIcon} alt="Java Icon" class="w-8 h-8" />
      <img src={ReactIcon} alt="React Icon" class="w-8 h-8" />
    </footer>
  </div>
</div>
