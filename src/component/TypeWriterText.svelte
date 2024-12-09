<script lang="ts">
  import { onMount } from "svelte";

  export let phrases: string[];
  export let speed: number = 200; 
  export let blinkSpeed: number = 500; 
  
  let currentPhraseIndex = 0;
  let typedChars = "";
  let isDeleting = false; 
  let currentPhrase = "";

  const typingPause = 1000; 
  const deletingPause = 500; 

  onMount(() => {
    if (!phrases || phrases.length === 0) {
      console.log("No phrases passed to TextTypeWriter");
      return;
    }

    currentPhrase = phrases[currentPhraseIndex];
    typeOrDelete();
  });

  function typeOrDelete() {
    const targetLength = isDeleting ? 0 : currentPhrase.length;
    const currentLength = typedChars.length;

    if (!isDeleting && currentLength < targetLength) {
      typedChars = currentPhrase.slice(0, currentLength + 1);
    } else if (!isDeleting && currentLength === targetLength) {
      setTimeout(() => {
        isDeleting = true;
        typeOrDelete();
      }, typingPause);
      return;
    } else if (isDeleting && currentLength > targetLength) {
      typedChars = typedChars.slice(0, currentLength - 1);
    } else if (isDeleting && currentLength === targetLength) {
      isDeleting = false;
      currentPhraseIndex = (currentPhraseIndex + 1) % phrases.length;
      currentPhrase = phrases[currentPhraseIndex];
      setTimeout(() => {
        typeOrDelete();
      }, deletingPause);
      return;
    }

    const delay = speed + Math.random() * 100; 
    setTimeout(typeOrDelete, delay);
  }
</script>

<style>
  .h2 {
    display: inline-block;
    font-size: 2rem;
    font-family: monospace;
    white-space: nowrap;
    overflow: hidden;
  }

  .cursor {
    display: inline-block;
    width: 1ch;
    animation: blink var(--blink-speed, 0.5s) step-end infinite alternate;
    text-align: left;
  }

  @keyframes blink {
    0% { opacity: 1; }
    100% { opacity: 0; }
  }
</style>

<h2 class="h2">
  {typedChars}<span class="cursor" style={`--blink-speed: ${blinkSpeed}ms;`}>|</span>
</h2>
