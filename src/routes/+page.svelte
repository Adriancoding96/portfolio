<script lang="ts">
  import TypeWriterText from "../component/TypeWriterText.svelte";
  import SocialMediaBar from "../component/SocialMediaBar.svelte";
  import ProjectGrid from "../component/ProjectGrid.svelte";
  import { Avatar } from '@skeletonlabs/skeleton';
  import '@fortawesome/fontawesome-free/css/all.min.css'
  
  let phrases: string[] = ["Back-end Developer", "Software Engineer", "Nerd"];
  let scroll: number = 0;
  let speed: number = 4;
</script>

<svelte:window bind:scrollY={scroll}/>

<div 
  class="container mx-auto flex p-24 h-screen"
  style:transform={`translate3d(0, ${scroll * speed}px, 0)`}
>
  <div class="flex justify-center items-center p-12">
    <Avatar 
      src="/profile.jpg" 
      width="w-64" 
      rounded="rounded-3xl" 
    />
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

<!-- Projects Section -->
<div class="container mx-auto py-16 h-screen" style:transform={`translate3d(0, ${scroll * -2}px, 0)`}>
  <ProjectGrid />
</div>

<style>
  
</style>
