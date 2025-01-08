<script lang="ts">
  import { onMount } from 'svelte';

  import javascriptIcon from 'devicon/icons/javascript/javascript-original.svg';
  import JavaIcon from 'devicon/icons/java/java-original.svg';
  import SpringIcon from 'devicon/icons/spring/spring-original.svg';
  import MavenIcon from 'devicon/icons/maven/maven-original.svg';
  import SqlIcon from 'devicon/icons/mysql/mysql-original.svg';
  import DockerIcon from 'devicon/icons/docker/docker-original.svg';
  import AwsIcon from 'devicon/icons/amazonwebservices/amazonwebservices-original-wordmark.svg';
  import RustIcon from 'devicon/icons/rust/rust-original.svg';
  import TypescriptIcon from 'devicon/icons/typescript/typescript-original.svg';
  import HtmlIcon from 'devicon/icons/html5/html5-original.svg';
  import CssIcon from 'devicon/icons/css3/css3-original.svg';
  import TailwindIcon from 'devicon/icons/tailwindcss/tailwindcss-original.svg';
  import SvelteIcon from 'devicon/icons/svelte/svelte-original.svg';
  import ReactIcon from 'devicon/icons/react/react-original.svg';
  import CppIcon from 'devicon/icons/cplusplus/cplusplus-original.svg';
  import LinuxIcon from 'devicon/icons/linux/linux-original.svg';
  import VimIcon from 'devicon/icons/vim/vim-original.svg';
  import GitIcon from 'devicon/icons/git/git-original.svg';
  import PostmanIcon from 'devicon/icons/postman/postman-original.svg';
  import LuaIcon from 'devicon/icons/lua/lua-original.svg';

  const ICON_COUNT = 20;
  const COLUMNS = 5;
  const ICON_SIZE = 100;

  export let horizontalGap: number = 180;
  export let verticalGap: number = 40;

  export let iconSrcs: string[] = [
    JavaIcon,
    SpringIcon,
    MavenIcon,
    SqlIcon,
    DockerIcon,
    AwsIcon,
    RustIcon,
    javascriptIcon,
    TypescriptIcon,
    HtmlIcon,
    CssIcon,
    TailwindIcon,
    SvelteIcon,
    ReactIcon,
    CppIcon,
    LinuxIcon,
    VimIcon,
    GitIcon,
    PostmanIcon,
    LuaIcon,
  ];

  if (iconSrcs.length < ICON_COUNT) {
    const defaultIcon = javascriptIcon;
    while (iconSrcs.length < ICON_COUNT) {
      iconSrcs.push(defaultIcon);
    }
  }

  interface Icon {
    id: number;
    src: string;
    animationDelay: number;
  }

  let rows: Icon[][] = [];

  onMount(() => {
    const icons: Icon[] = Array.from({ length: ICON_COUNT }, (_, i) => ({
      id: i + 1,
      src: iconSrcs[i % iconSrcs.length],
      animationDelay: Math.random() * 5,
    }));

    rows = [];
    for (let i = 0; i < ICON_COUNT; i += COLUMNS) {
      rows.push(icons.slice(i, i + COLUMNS));
    }
  });
</script>

<style>
  .container {
    display: flex;
    flex-direction: column;
    align-items: center; /* Center rows horizontally */
    width: 100%;
    height: 100vh;
    overflow: hidden;
    padding-right: 160px;
  }

  .row {
    display: flex;
    justify-content: center;
    gap: var(--horizontal-gap, 24px); 
    margin-bottom: var(--vertical-gap, 40px);
  }

  .row.shifted {
    transform: translateX(calc(var(--icon-size) / 2 + var(--horizontal-gap) / 2));
  }

  .icon {
    width: var(--icon-size);
    height: var(--icon-size);
    display: flex;
    align-items: center;
    transition: transform 0.3s ease;
    animation: bobbing 3s ease-in-out infinite;
    cursor: pointer;
  }

  .icon img {
    max-width: 75%;
    transition: transform 0.3s ease;
  }

  .icon:hover {
    transform: scale(1.5);
    z-index: 10; /* Bring to front on hover */
  }

  .icon:hover img {
    transform: scale(1.125);
  }

  @keyframes bobbing {
    0% { transform: translateY(0px); }
    50% { transform: translateY(-10px); }
    100% { transform: translateY(0px); }
  }

  @media (max-width: 600px) {
    .icon {
      width: calc(var(--icon-size) * 0.8);
      height: calc(var(--icon-size) * 0.8);
    }

    .icon img {
      max-width: 60%;
    }

    .icon:hover img {
      transform: scale(1.125);
    } 

    .row.shifted {
      transform: translateX(calc(var(--icon-size) / 2 * 0.8 + var(--horizontal-gap) / 2));
    }
  }
</style>

<div class="flex justify-center pb-24">
  <h1 class="h1">Technologies</h1>
</div>
<div
  class="container"
  style="
    --icon-size: {ICON_SIZE}px;
    --horizontal-gap: {horizontalGap}px;
    --vertical-gap: {verticalGap}px;
  "
>
  {#each rows as row, rowIndex}
    <div class="row {rowIndex % 2 === 1 ? 'shifted' : ''}">
      {#each row as icon}
        <div
          class="icon"
          style="animation-delay: {icon.animationDelay}s;"
          tabindex="-1"
          aria-label="Icon {icon.id}"
        >
          <img src={icon.src} alt="Devicon Icon" />
        </div>
      {/each}
    </div>
  {/each}
</div>
