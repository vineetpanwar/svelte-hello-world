<script>
	import {slide, fade ,blur} from "svelte/transition" 
	import Surname from "./surname.svelte";
	import TagLineGenerator from "./tagLineGenerator.svelte";
	import DemoCompo from "./DemoCompo.svelte";
	import Box from "./box.svelte";
	let vineet = "vineet";
	let stringToShow = "";
	let htmlToShow = "";
	let bindChecked = false;
	let counter = 0;
	$: squared = counter ** 2;
	const handleClick = () => {
		counter ++;
	}
	let cities=[
		{id:1,name:'banagalore'},
		{id:2,name:'delhi'},
		{id:3,name:'gurgaion'}
	];

	const getStarWarInfo = async() => {
		const randomNum = Math.floor(Math.random() * 10) + 1;
		const starwarResponse = await fetch(`https://swapi.co/api/people/${randomNum}/`);
		return await starwarResponse.json()
	}
	let promise = getStarWarInfo()
</script>
	{#await promise}
	<h1>loading...</h1>
	{:then character}
	<h1>{character.name}</h1>
	{/await}

	<form>
		<div class="username">
			<label for="username">Enter your username:</label>
			<input type="text" name="username" placeholder="username here" />
		</div>
		<div class="password">
			<label for="password">Enter your password:</label>
			<input type="password" name="password" />
		</div>
		<label>
			<input type="checkbox" bind:checked={bindChecked} />
			do you wanna login ?
		</label>
	</form>

	{#if bindChecked}
		<h1 transition:blur={{duration:1200,delay:100}}>okay,getting you in </h1>
	{/if}

	{#each cities as {name,id},index}
		<li>{id}:{name}</li>
	{/each}

	<button on:click={handleClick}>Counter:{counter}</button>
	<h1>the square of the counter is {squared}</h1>
	<Box>
	<h1 slot="header">Hello</h1>
	<div slot="body">
		<span  class="vineet">My first name is-{vineet}</span>
		<Surname  lastName="abcd"/>
		<TagLineGenerator  tagLine={"hello this is vineet panwar"} />
		<textarea bind:value={stringToShow} />
		<textarea bind:value={htmlToShow} />
		<p>{stringToShow}</p>
		{@html htmlToShow}
	</div>	
	<div slot="footer">
		<DemoCompo />
	</div>
	</Box>
	

<style>
	.vineet{
		font-size:50px;
		color:blue;
	}

</style>