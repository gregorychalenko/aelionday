<script>
	import Prophecy from './Prophecy.svelte';
	export let prophecy_list;
	export let search = '';

	$: prophecy_filtered_list = prophecy_list.filter(i => i.text.indexOf(search) !== -1);
</script>

<body>
	<h1>Ambitious</h1>
	<input bind:value={ search } on:change placeholder="Search by word"/>
	<ul class="prophecy">
		{#each prophecy_filtered_list as prophecy}
			<Prophecy { ...prophecy }/>
		{/each}
	</ul>

</body>

<style>
:global(html) {
	background-color: black;
	color: white;
	font-family: 'Courier New', Courier, monospace;
}

body {
	background-color: black;
	color: white;
}

h1 {
	height: 5em;
	font-family: 'Courier New', Courier, monospace;
	font-weight: lighter;
	text-align: bottom;
	line-height: 9em;
	text-transform: uppercase;
	text-align: right;
	color: rgba(0, 0, 0, 0.7);
	text-shadow: 0 0 1px gold;
	background-image: url(https://sf.my.games/sites/sf.my.com/files/styles/sf_news_prime/public/news_cap_1240x310_17.jpg?itok=0d7DQzBd);
	background-repeat: no-repeat;
	max-width: 1240px;
}

input {
	display: block;
	width: 100%;
	margin-top: -3.5em;
	background: rgba(0, 0, 0, 0.4);
	border: 0 none;
	outline: 0 none;
	color: white;
	border-radius: 0;
}

ul {
	margin: 0;
	padding: 0;
}
</style>