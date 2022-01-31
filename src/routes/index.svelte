
<script>
    import { onMount } from "svelte";
    import axios from "axios";
    import Card from "../components/Card.svelte";
    const restServer = 'http://localhost:5000'
    const endpoint ='/movies';
    let movies = [];

    onMount(async function () {
        const response = await axios.get(restServer+endpoint);
        console.log(response.data);
        movies = response.data;
    });
</script>

<main class="px-4">
<div class="w-full bg-cover bg-center" style="height:32rem; background-image: url(https://images.unsplash.com/photo-1524985069026-dd778a71c7b4?ixid=MnwxMTgzMzd8MHwxfGFsbHx8fHx8fHx8fDE2NDI2NDE1MDQ&ixlib=rb-1.2.1&auto=format&fit=crop&w=1050&q=80);">
    <div class="flex items-center justify-center h-full w-full bg-gray-900 bg-opacity-50">
        <div class="text-center">
            <h1 class="text-white -mt-32 text-2xl font-semibold uppercase md:text-3xl">Welcome to my movies site <span class="underline text-blue-400">movies</span> site</h1>
<!--             <button class="mt-4 px-4 py-2 bg-blue-600 text-white text-sm uppercase font-medium rounded hover:bg-blue-500 focus:outline-none focus:bg-blue-500">Start project</button>
-->     </div>
    </div>
</div>

<h2 class="text-center mt-4">Here are some of my favorite movies</h2>
{#each movies as movie}
    <div class="mt-4 flex flex-row flex-wrap">
      <Card
        name="{movie.name}"
        genres="{movie.genres}"
        casts="{movie.casts}"
        poster="{movie.poster}"
        director="{movie.director}"
        release_date="{movie.release_date}"
        restServer="{restServer}"
        director_avatar="{movie.director_avatar}"
        />
    </div>
  {/each}

  </main>