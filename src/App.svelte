<script lang="ts">
import HarmonyGrid from './HarmonyGrid.svelte'
import GuitarNeck from './GuitarNeck.svelte'
import DiatonicHarmony from './DiatonicHarmony.svelte';
// import NoteSelector from './noteSelector.svelte';
// import {makeScale} from './ScaleToChord.svelte';
// import {getMode, makeDiatonicChords} from './Functions.svelte'
// import { chromaticScales, romanNumerals } from "./Constants.svelte";

// let cMajor = makeScale(chromaticScales.flats, "major")
// let cMinor = makeScale(chromaticScales.flats, "major")
// let fMinor = makeScale(getMode(chromaticScales.flats, 6), "minor")

// let chromatic = getMode(chromaticScales.sharps, 6)
// let fLydian = getMode(cMajor, 4)


// let cMajorChords = makeDiatonicChords(cMajor, 4)
// console.log(cMajorChords);


</script>

<h1>Guitar Sudoku</h1>

<DiatonicHarmony/>

<!-- <h2>the makeScale() function</h2>

<p>C Major: {cMajor}</p>
<p>C minor: {cMinor}</p>
<p>chromatic {chromatic}</p>
<p>F lydian mode: {fLydian}</p>
<p>F minor: {fMinor}</p> 

<div class="docs">

	<h2>Make Diatonic chords</h2>
	<p>
		The <b>makeDiatonicChords()</b> function takes scale (Array) and notesInChord (number) 	as arguments.This function runs a map method on the scale array, wich passes the getMode() function, with scale and the "index", added by 1, as arguments thru the makeChord() function, together with "noteInChord". The return is a nested a array populated by arrays of note names of each chord.  
	
	</p>
</div>

{ #each cMajorChords as chord, o }
 <div class="diatonic-chord" >
	 <p class="roman-numerals">{romanNumerals.majorScale[o]}</p>
   { #each chord as note, i }
    <p 
	class="note" 
	style="background-color: hsl({(i * 51) + (o * 153)}, 50%, 65%)"
	>
	{note}, </p>
  { /each }
</div>
{ /each } -->


<GuitarNeck/>
<!-- <div class="selectors">
	<NoteSelector kind="pink"/> 
	<NoteSelector kind="skyblue"/>
	<NoteSelector kind="salmon"/>
	<NoteSelector kind="lightgreen"/>
	<NoteSelector kind="aquamarine"/>
	<NoteSelector kind="goldenrod"/>
</div> -->


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
	/> 
	<HarmonyGrid  chordName="Am"/>
</div>


<style>
	 * {padding: 0;}

	/* .selectors {
		display: flex;
		flex-direction: row;
	} */

	.chordsheet {
		display: flex;
		flex-direction: row;
	}

	.diatonic-chord {
		display: flex;
		flex-direction: row;
		justify-content: space-evenly;
		align-items: center;
		max-width :100px;
		margin-bottom: .5em;
		margin-left: 2em;
	}
	.note {
		display: inline;
		margin-right: .5rem;
		padding: .5em;		
		
	}

	.docs {
		max-width: 600px;
	}

	.roman-numerals {
		min-width: 40px;
		margin-left: 3em; 
		padding-right: 1em;
		font-weight: bold;
		

	}
</style>