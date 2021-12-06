
<script lang="ts" context="module">
import {chromaticFullRangeFlats, chromaticFullRangeSharps } from './Constants.svelte'
import { guitarNeck } from './GuitarNeck.svelte'
import { flats } from './stores'

let accidentals : boolean

flats.subscribe(value => {
	accidentals = value
})


let selected = ""
let chromatic = accidentals ? chromaticFullRangeFlats : chromaticFullRangeSharps    
const noteRange =  [guitarNeck[5][0][0], guitarNeck[0][0][21]]
const notesOnNeck = chromatic.slice(chromatic.indexOf(noteRange[0]), chromatic.indexOf(noteRange[1]))



function handleChange() {
	document.querySelectorAll(".pink").forEach(el => el.classList.remove("pink"))
	
	let selector = "." + selected
	let aClass = document.querySelectorAll(selector)
	let selectedNote = []

	aClass.forEach( item => {
		
		selectedNote.push(item)
	})
	
	selectedNote.forEach(item => item.classList.add("pink"))
}
</script>


<div class="note-selector">
    <select bind:value={selected} on:change={handleChange} name="pink" id="note1">
        {#each notesOnNeck as notes, i}
        <option value={notes}>{notes}</option>
        {/each}
      </select>
</div>


<style>

.note-selector {
  margin-top: 4em;
}




</style>