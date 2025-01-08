<script lang="ts">
  import TypeWriterText from "../component/TypeWriterText.svelte";
  import SocialMediaBar from "../component/SocialMediaBar.svelte";
  import ProjectGrid from "../component/ProjectGrid.svelte";
  import TechGrid from "../component/TechGrid.svelte";
  import Contact from "../component/Contact.svelte";
  import About from "../component/About.svelte";
  import { Avatar } from '@skeletonlabs/skeleton';
  import '@fortawesome/fontawesome-free/css/all.min.css'
  
  let phrases: string[] = ["Back-end Developer", "Software Engineer", "Nerd"];
</script>

<!-- The outer container with scroll snapping enabled -->
<div class="outer-container">
  <section class="section">
    <div class="container mx-auto flex p-24 h-full">
      <div class="flex justify-center items-center p-12">
        <Avatar src="/profile.jpg" width="w-64" rounded="rounded-3xl" />
      </div>
      <div class="w-1/2 flex flex-col justify-center space-y-4 pr-8">
        <h1 class="text-4xl font-bold">Hello, I am Adrian</h1>
        <div class="h-10">
          <TypeWriterText {phrases} />
        </div>
        <div>
          <SocialMediaBar />
        </div>
        <div>
          <a href="/" class="btn variant-soft mt-4 w-44 flex items-center space-x-2">
            <i class="fa-regular fa-file"></i>
            <span>Resume</span>
          </a>
        </div>
      </div>
    </div>
  </section>

  <section class="section">
    <div class="container mx-auto py-16 h-full">
      <About />
    </div>
  </section>
  <section class="section">
    <div class="container mx-auto py-16 h-full">
      <TechGrid />
    </div>
  </section>
  <section class="section">
    <div class="container mx-auto py-16 h-full">
      <ProjectGrid />
    </div>
  </section>

  <section class="section">
    <div class="container mx-auto py-16 h-full">
      <Contact />
    </div>
  </section>
</div>

<style>
  /* Make the outer container full height and enable vertical scrolling */
  .outer-container {
    height: 100vh;               /* Full viewport height */
    overflow-y: scroll;          /* Enable vertical scrolling */
    scroll-snap-type: y mandatory; 
    -webkit-overflow-scrolling: touch;
  }

  /* Each section should snap at the start of scroll */
  .section {
    scroll-snap-align: start; 
    height: 100vh;              /* Ensure each section is exactly one viewport height */
  }
</style>
