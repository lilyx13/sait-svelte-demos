<script>
	import PageHeader from '../../lib/components/PageHeader.svelte';
	import ListItem from '../../lib/components/ListItem.svelte';
	let listItems = ['car', 'bike', 'scooter ', 'imperial star destroyer'];
	let secondList = [
		{ name: 'Alfred', species: 'Dog', href: '/' },
		{ name: 'Elvira', species: 'Cat', href: '/' },
		{ name: 'Sally', species: 'Crow', href: '/' },
		{ name: 'Gus', species: 'Ferret', href: '/' }
	];
	const headerInfo = {
		title: 'About Page',
		description: '',
		bgColor: 'bg-yellow-500'
	};
</script>

<PageHeader {...headerInfo}>
	<h3 slot="info">
		Lorem ipsum dolor sit amet consectetur adipisicing elit. Saepe ad et non voluptatem distinctio
		expedita. Quaerat distinctio quam expedita. Quae.
	</h3>
</PageHeader>

<section>
	<h2 class="text-3xl">Our Example List</h2>
	<ul class="list-disc ml-8">
		{#each listItems as item}
			<ListItem bgColor="bg-red-200">{item}</ListItem>
		{/each}
	</ul>
</section>

<section>
	<h2 class="text-3xl">Animals</h2>
	<ul>
		{#each secondList as { href, name, species }}
			<ListItem bgColor="bg-blue-200"><a {href}>{name} is a {species}</a></ListItem>
		{/each}
	</ul>
</section>
