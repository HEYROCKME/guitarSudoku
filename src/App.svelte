<script lang="ts">
import HarmonyGrid from './HarmonyGrid.svelte'
import GuitarNeck from './GuitarNeck.svelte'
import NoteSelector from './noteSelector.svelte';



 
</script>

<GuitarNeck/>
<div class="selectors">
	<NoteSelector kind="pink"/> 
	<NoteSelector kind="skyblue"/>
	<NoteSelector kind="salmon"/>
	<NoteSelector kind="lightgreen"/>
	<NoteSelector kind="aquamarine"/>
	<NoteSelector kind="goldenrod"/>
</div>


<h1>Harmony</h1>
<div class="chordsheet">
	<HarmonyGrid /> <HarmonyGrid />
</div>


<style>
	 * {padding: 0;}

	.selectors {
		display: flex;
		flex-direction: row;
	}

	.chordsheet {
		display: flex;
		flex-direction: row;
	}

	
</style>