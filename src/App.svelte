<script lang="ts">
import HarmonyGrid from './HarmonyGrid.svelte'
import GuitarNeck from './GuitarNeck.svelte'
import NoteSelector from './noteSelector.svelte';
import {makeScale} from './ScaleToChord.svelte';


import {getMode, makeChord} from './Functions.svelte'
import { chromaticScales } from "./Constants.svelte";

let cMajor = makeScale(chromaticScales.flats, "major")
let cMinor = makeScale(chromaticScales.flats, "major")
let fMinor = makeScale(getMode(chromaticScales.flats, 6), "minor")

let chromatic = getMode(chromaticScales.sharps, 6)
let fLydian = getMode(cMajor, 4)




// Suggestion: notesInChord can be set to an enum 1 - 6 
function makeDiatonicChords(scale : string[], notesInChord : number ) {
  let diatonicChords = []
  scale.forEach((note, index, array) => { 
    let chord = makeChord(getMode(scale, index + 1 ), notesInChord)
	diatonicChords.push(chord)
})

return diatonicChords


}
let cMajorChords = makeDiatonicChords(cMajor, 3)
console.log(cMajorChords);


</script>

<h1>Guitar Sudoku</h1>

<h2>the makeScale() function</h2>

<p>C Major: {cMajor}</p>
<p>C minor: {cMinor}</p>
<p>chromatic {chromatic}</p>
<p>F lydian mode: {fLydian}</p>
<p>F minor: {fMinor}</p> 

<h2>Make chords</h2>
<p></p>

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
	<HarmonyGrid chordName="Em" 
	strings =  {[
          {openString: "e", stringNum: 1, fret: "0", noteName: "e", harmony: "r", note: "e3"},
          {openString: "b", stringNum: 2, fret: "0", noteName: "b", harmony: "5", note: "b2"},
          {openString: "g", stringNum: 3, fret: "0", noteName: "g", harmony: "b3", note:"g2" },
          {openString: "d", stringNum: 4, fret: "2", noteName: "e", harmony: "r",  note:"e2"},
          {openString: "a", stringNum: 5, fret: "2", noteName: "b", harmony: "5", note: "b1"},
          {openString: "e", stringNum: 6, fret: "0", noteName: "e", harmony: "r", note: "e1"}
                      ]}
	/> <HarmonyGrid  chordName="Am"/>
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