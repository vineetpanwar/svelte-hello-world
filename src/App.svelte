<script>
	import Surname from "./surname.svelte";
	import TagLineGenerator from "./tagLineGenerator.svelte";
	import DemoCompo from "./DemoCompo.svelte";
	import Box from "./box.svelte";
	let vineet = "vineet";
	let stringToShow = "";
	let htmlToShow = "";
</script>

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