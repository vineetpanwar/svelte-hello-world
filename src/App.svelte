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
</script>
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