<script>
	import { onMount } from 'svelte';

	let scripts = 'no';
	onMount(() => {
		scripts = 'yes';
	});
</script>

<span>script? {scripts}</span>
<nav>
	<a href=".">root</a>
	<a href="#a">link-A</a>
	<a href="#b">link-B</a>
	<a href="#c">link-C</a>
	<a href="#d">link-D</a>
</nav>
<pre>
  hmm this doens't seem to reproduce the issue
  --
  To reproduce:
  0. clear history 
  1. navigat some using the nav creating a decent sized history
  2. go back to the root 
  3. start using history back and see that the 
  position stops becoming updated after a certain amount of "history back's"
  
  --
  if you "history back or forth "
</pre>
<section id="a" style:background-color="green">A</section>
<section id="b" style:background-color="blue">B</section>
<section id="c" style:background-color="red">C</section>
<section id="d" style:background-color="teal">D</section>
<section id="e" style:background-color="brown">E</section>

<style>
	:global(html) {
		scroll-behavior: smooth;
	}
	:global(body) {
		background-color: aliceblue;
		display: flex;
		gap: 5px;
		flex-direction: column;
		align-items: center;

		font-size: 2em;
	}
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		width: 100%;
		height: 100vh;
		color: white;
		background-color: rgb(197, 186, 186);
	}
	nav {
		top: 0;
		left: 0;
		background-color: aliceblue;
		position: fixed;
		display: flex;
		gap: 5px;
	}
	a {
		padding: 5px;
	}
</style>
