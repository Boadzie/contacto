<script context="module">
	export async function load({fetch}){
           const res = await fetch("https://jsonplaceholder.typicode.com/users")
		   const users = await res.json()
		//    console.log(users)
		   return {
			   props: {
				   users
			   }
		   }
		   
	}
 

</script>
<script>
	export let users
</script>
<main class="container mx-auto px-4 py-4">
	<h1 class="text-center py-8 uppercase tracking-widest text-5xl font-extrabold text-transparent bg-clip-text bg-gradient-to-br from-blue-400 to-red-600">Contacto</h1>
	<div class="flex justify-center items-center min-h-screen">
		<div class="grid grid-cols-1 gap-4 max-w-5xl w-full lg:grid-cols-2">
			{#each users as user }
				  <a href={`/${user.id}`} class="bg-gray-900 p-4 duration-300  transition ease-in-out delay-150 hover:-translate-y-1 hover:scale-110 rounded-lg text-white shadow-md">
					<svg class="w-14 h-14" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5.121 17.804A13.937 13.937 0 0112 16c2.5 0 4.847.655 6.879 1.804M15 10a3 3 0 11-6 0 3 3 0 016 0zm6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
					<h2 class="text-3xl inline-flex items-center py-2 font-bold">
						
						{user.name}</h2>
						<br>
					<p class="text-cyan-100 inline-flex items-center">
						<svg class="w-6 h-6 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path></svg>
						{user.email}</p>
						<br>
					<p class="text-cyan-100 inline-flex items-center">
						<svg class="w-6 h-6 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"></path></svg>
						{user.phone}</p>
						<br>
					<p class="font-bold inline-flex items-center">
						<svg class="w-6 h-6 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"></path></svg>
						{user.address.city}</p>
				  </a>
			   
			{/each}
		</div>
	</div>
</main>
