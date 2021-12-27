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
				  <a href={`/${user.id}`} class="bg-gray-900 p-4 rounded-lg text-white shadow-md">
					<h2 class="text-3xl py-2 font-bold">{user.name}</h2>
					<p class="text-cyan-100">{user.email}</p>
					<p class="text-cyan-100">{user.phone}</p>
					<p class="font-bold">{user.address.city}</p>
				  </a>
			   
			{/each}
		</div>
	</div>
</main>
