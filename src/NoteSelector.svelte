<script lang="ts">
import {chromaticFullRangeFlats, chromaticFullRangeSharps } from './Constants.svelte'
import { guitarNeck } from './GuitarNeck.svelte'
import {onMount} from 'svelte'
import { flats, color } from './stores'

export let kind = "blue"

let accidentals : boolean
let select = ""

flats.subscribe(value => {
	accidentals = value
})



color.subscribe(value => 
kind = value
)


color.set(kind)
const cssColor = kind

console.log(kind);


	

let chromatic = accidentals ? chromaticFullRangeFlats : chromaticFullRangeSharps    
const noteRange =  [guitarNeck[5][0].noteName, guitarNeck[0][21].noteName]
const notesOnNeck = chromatic.slice(chromatic.indexOf(noteRange[0]), chromatic.indexOf(noteRange[1]))





function handleChange() {
	document.querySelectorAll("."+cssColor).forEach(el => el.classList.remove(cssColor))
	
	let selector = "." + select
	let aClass = document.querySelectorAll(selector)
	let selectedNote = []

	aClass.forEach( item => {	
		selectedNote.push(item)
	})
		selectedNote.forEach(item => item.classList.add(cssColor))
}


</script>


<div class="note-selector" {kind}>
    <select bind:value={select} on:change={handleChange} name="notes" id="note1">
		<option value="" selected hidden>note</option>
        {#each notesOnNeck as notes, i}
          <option value={notes.length <= 2 ? notes : notes.replace("#", "sharp")}>{notes}</option>
        {/each}
      </select>
</div>


<style>

.note-selector {
  margin-top: 4em;
}




</style>