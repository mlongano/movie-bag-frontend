<script>
    export let name;
    export let casts;
    export let genres;
    export let poster;
    export let director;
    export let director_avatar;
    export let release_date;
    export let restServer;
</script>
<div class="max-w-sm w-full lg:max-w-full lg:flex">
  <div class="h-48 lg:h-auto lg:w-48 flex-none bg-cover rounded-t lg:rounded-t-none lg:rounded-l text-center overflow-hidden" style="background-image: url({restServer+poster})" title="{name}">
  </div>
  <div class="border-r border-b border-l border-gray-400 lg:border-l-0 lg:border-t lg:border-gray-400 bg-white rounded-b lg:rounded-b-none lg:rounded-r lg:w-48 p-4 flex flex-col justify-between leading-normal shadow-lg">
    <div class="mb-8">
      <p class="text-sm text-gray-600 flex items-center">
        <svg class="fill-current text-gray-500 w-3 h-3 mr-2" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20">
          <path d="M4 8V6a6 6 0 1 1 12 0v2h1a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2v-8c0-1.1.9-2 2-2h1zm5 6.73V17h2v-2.27a2 2 0 1 0-2 0zM7 6v2h6V6a3 3 0 0 0-6 0z" />
        </svg>



          {#each genres as genre}
              <span>{genre}</span>
          {/each}
      </p>
      <div class="text-gray-900 font-bold text-xl mb-2">{name}</div>
      <p class="text-gray-700 text-base font-bold">Cast:
          <ul class="border rounded-md w-fit p-1 shadow-lg">
          {#each casts as actor}
              <li class="even:bg-gray-200">{actor}</li>
          {/each}
          </ul>
    </div>
    <div class="flex items-center">
      <img class="w-10 h-10 rounded-full mr-4" src="{restServer+director_avatar}" alt="{director}">
      <div class="text-sm">
        <p class="text-gray-900 leading-none">{director}</p>
        <p class="text-gray-600">{release_date}</p>
      </div>
    </div>
  </div>
</div>