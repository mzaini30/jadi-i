<div class="container">
	<div class="my-3">
		<textarea class="form-control" readonly placeholder="Output" bind:this={tinggi1} bind:value={output}></textarea>
	</div>
	<div class="mb-3">
		<textarea class="form-control" placeholder="Input" bind:this={tinggi2} bind:value={input}></textarea>
	</div>
</div>

<script>
	let [input, output] = ["", ""]
	let tinggi1
	let tinggi2
	import {onMount} from "svelte"
	const ubahTinggi = () => {
		const berubah = () => {
			let tingginya = `${window.innerHeight / 2 - 25}px`
			tinggi1.style.height = tingginya
			tinggi2.style.height = tingginya
		}
		berubah()
		window.addEventListener("resize", berubah)
	}
	onMount(() => ubahTinggi())
	$: output = input.replace(/[aiueo]/g, "i").replace(/[AIUEO]/g, "I")
</script>
