<script lang="ts">
import {chromaticFullRangeFlats, chromaticFullRangeSharps } from './Constants/Scales.svelte'
import { guitarNeck } from './NeckMaker.svelte'
import { flats } from './stores'
export let kind = "transparent"

let noteSelector


let select = ""
let cssColor : string
cssColor = kind

let accidentals : boolean
flats.subscribe(value => {
	accidentals = value
})

	
let chromatic = accidentals ? chromaticFullRangeFlats : chromaticFullRangeSharps    
const noteRange =  [guitarNeck[5][0].noteName, guitarNeck[0][21].noteName]
const notesOnNeck = chromatic.slice(chromatic.indexOf(noteRange[0]), chromatic.indexOf(noteRange[1]))
document.querySelectorAll(".note-selector").forEach((select)=> {select.classList.add(cssColor)})

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


<div bind:this="{noteSelector}" class="note-selector {kind}" {kind}>
    <select bind:value={select} on:change={handleChange} name="notes" id="note1">
		<option value="" selected hidden>note</option>
        {#each notesOnNeck as notes, i}
          <option value={notes.length <= 2 ? notes : notes.replace("#", "sharp")}>{notes}</option>
        {/each}
      </select>
</div>


<style>
select {
appearance: none;
}
.note-selector {
  margin-top: 4em;
}

.pink  {background-color:  pink;}
.salmon {background-color: salmon;}
 .skyblue {background-color: skyblue;}
 .lightgreen {background-color: lightgreen;}
 .sandybrown {background-color: sandybrown;}
 .aquamarine {background-color: aquamarine;}
 .goldenrod {background-color: goldenrod;}



</style>