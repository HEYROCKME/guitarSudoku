<script lang="ts">



import HarmonyGrid from './HarmonyGrid.svelte'
import GuitarNeck from './GuitarNeck.svelte'
import NoteSelector from './NoteSelector.svelte';





// let frets = 21
// let flats = false
// let guitarneck = makeGuitarNeck(tuning.regular, frets, flats)



// let selected = ""
// let chromatic = flats ? chromaticFullRangeFlats : chromaticFullRangeSharps    

// const noteRange =  [guitarneck[guitarneck.length -1][0][0], guitarneck[0][0][21]]
// const notesOnNeck = chromatic.slice(chromatic.indexOf(noteRange[0]), chromatic.indexOf(noteRange[1]))



// function handleChange() {
// 	document.querySelectorAll(".pink").forEach(el => el.classList.remove("pink"))
	
// 	let selector = "." + selected
// 	let aClass = document.querySelectorAll(selector)
// 	let selectedNote = []

// 	aClass.forEach( item => {
		
// 		selectedNote.push(item)
// 	})
	
// 	selectedNote.forEach(item => item.classList.add("pink"))
// }


 

</script>

<!-- <h1>Guitar neck</h1>
<table>
  {#each guitarneck as fretboard, i }

	 <tr id="string{i + 1}">
	{#each fretboard as notes }
	<td class="string-names">{i + 1} str</td>
		{#each notes as note}
	
		<td class={note}>{note}</td>

		{/each}
	{/each}
	</tr>	
  {/each}
</table> -->


<!-- <select bind:value={selected} on:change={handleChange} name="pink" id="note1">
  {#each notesOnNeck as notes}
  <option value={notes}>{notes}</option>
  {/each}
</select> -->


<GuitarNeck/>
<NoteSelector/>



<h1>Harmony</h1>
<div class="chordsheet">
	<HarmonyGrid/> <HarmonyGrid/>
</div>


<style>
	 * {padding: 0;}



	.chordsheet {
		display: flex;
		flex-direction: row;
	}

	
</style>