<script context="module">
	export async function load({fetch, page}){
        const {id} = page.params;
        const res = await fetch(`https://jsonplaceholder.typicode.com/users/${id}`);
        const user = await res.json()
		//    console.log(users)
		   return {
			   props: {
				   user
			   }
		   }
		   
	}
 

</script>
<script>
	export let user
</script>
<main class="container mx-auto px-4 py-4">
	<h1 class="text-5xl text-center py-5">Contacto</h1>
	<div class="mr-auto ml-auto max-w-2xl">
          <div class="bg-gray-900 p-6  rounded-lg text-white shadow-md">
			<h2 class="text-3xl font-bold py-2">{user.name}</h2>
			<p class="text-cyan-100">{user.email}</p>
            <p class="text-cyan-100">{user.phone}</p>
			<p class="font-bold">{user.address.city}</p>
		  </div>
	
</div>
</main>
