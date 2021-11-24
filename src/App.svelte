<script lang="ts">

import { getMode, makeMusicalSpectre, makeChord }  from './Functions.svelte'



const chromaticScales ={
	sharps: ["c", "c#", "d", "d#", "e", "f", "f#", "g", "g#", "a","a#","b"],
	flats: ["c", "db", "d", "eb", "e", "f", "gb", "g", "ab", "a","bb","b"]
}

 let majorScales = {
	 C: ["c", "d", "e", "f", "g", "a", "b"],
	 G: [ "g", "a", "b","c", "d", "e", "f#"],
	 D: [ "d", "e", "f#", "g", "a", "b", "c#"],
	 A: [ "a", "b", "c#", "d", "e", "f#", "g"],
	 E: [ "e", "f#", "g", "a", "b", "c#", "d"] 
	
 }
 



 let guitarNeck = {
  firstString: [ 
	  
	  { fret: 0, noteName: "e", note: "E3" },
	  { fret: 1, noteName: "f", note: "F3" },
	  { fret: 2, noteName: "f#", note: "F#3" },
	  { fret: 3, noteName: "g", note: "G3" },
	  { fret: 4, noteName: "g#", note: "G#3" },
	  { fret: 5, noteName: "a", note: "A3" },
	  { fret: 6, noteName: "a#", note: "A#3" },
	  { fret: 7, noteName: "b", note: "B3" },
	  { fret: 8, noteName: "c", note: "C4" },
	  { fret: 9, noteName: "c#", note: "C#4" },
	  { fret: 10, noteName: "d", note: "D4" },
	  { fret: 11, noteName: "d#", note: "D#4" },
	  { fret: 12, noteName: "e", note: "E4" },
	  { fret: 13, noteName: "f", note: "F4" },
	  { fret: 14, noteName: "f#", note: "F#4" },
	  { fret: 15, noteName: "g", note: "G4" },
	  { fret: 16, noteName: "g#", note: "G#4" },
	  { fret: 17, noteName: "a", note: "A4" },
	  { fret: 18, noteName: "a#", note: "A#4" },
	  { fret: 19, noteName: "b", note: "B4" },
	  { fret: 20, noteName: "c", note: "C5" },
	  { fret: 21, noteName: "c#", note: "C#5" },
	  { fret: 22, noteName: "d", note: "D5" },
	  { fret: 23, noteName: "d#", note: "D#5" },
	  { fret: 24, noteName: "e", note: "E5" },

	]
 }







let chromatic = getMode(chromaticScales.sharps, 5)

let twoOctaves = [...chromatic]
console.log(

twoOctaves
	
)

 const chord = { 
	  chordName: "Am", 
	  chordKey: "A natural minor",
	  chordTones: ["a", "c", "e"], 
	  harmonicFunction: "i",
	  scale: ["a", "b", "c", "d", "e", "f", "g"],
	  diatonicChords: ["i", "iib5", "III", "iv", "v", "bVI", "bVII" ],
	   strings: [
		{openString: "e", stringNum: 1, fret: "0", noteName: "e", harmony: "5", note: "e3"},
		{openString: "b", stringNum: 2, fret: "1", noteName: "c", harmony: "3", note: "c3" },
		{openString: "g", stringNum: 3, fret: "2", noteName: "a", harmony: "R", note:"a2" },
		{openString: "d", stringNum: 4, fret: "2", noteName: "e", harmony: "5",  note:"e2"},
		{openString: "a", stringNum: 5, fret: "0", noteName: "a", harmony: "R", note: "a1"},
		{openString: "e", stringNum: 6, fret: "x", noteName: "-", harmony: "-", note: ""}
					]
    }

class GuitarChord {
	chordName : string
	chordKey  : string
	harmonicFunction : string
	strings : {}[]
	scale : string[]



	constructor(chordName, chordKey, harmonicFunction, scale, strings ) {
		this.chordName = chordName
		this.chordKey = chordKey
		this.harmonicFunction = harmonicFunction
		this.strings = strings
		this.scale = scale
		

	}
}

// let aMinor = new GuitarChord("Am", "A natural minor", "i", chord.scale, chord.strings)
// console.log(aMinor)
</script>

<div class="guitarneck">
	{#each guitarNeck.firstString as {fret, noteName, note}, i }
  <li>
	  
	<ul>{note}</ul>

  </li>
  	
  {/each}

</div>

<div class="card">
  <h2>Harmony Grid</h2>
	<p class="key">Key: {chord.chordKey}</p>

	<div class="grid-card">
  	  
	  <table class="chord-grid">
		<tr>
			<td class="frets">{chord.strings[0].fret}</td>
			<td class="notes">{chord.strings[0].noteName}</td>
			<td class="harmony">{chord.strings[0].harmony}</td>
		</tr>
		<tr>
			<td class="frets">{chord.strings[1].fret}</td>
			<td class="notes">{chord.strings[1].noteName}</td>
			<td class="harmony">{chord.strings[1].harmony}</td>
		</tr>
		<tr>
			<td class="frets">{chord.strings[2].fret}</td>
			<td class="notes">{chord.strings[2].noteName}</td>
			<td class="harmony">{chord.strings[2].harmony}</td>
		</tr>
		<tr>
			<td class="frets">{chord.strings[3].fret}</td>
			<td class="notes">{chord.strings[3].noteName}</td>
			<td class="harmony">{chord.strings[3].harmony}</td>
		</tr>
		<tr>
			<td class="frets">{chord.strings[4].fret}</td>
			<td class="notes">{chord.strings[4].noteName}</td>
			<td class="harmony">{chord.strings[4].harmony}</td>
		</tr>
		<tr>
			<td class="frets">{chord.strings[5].fret}</td>
			<td class="notes">{chord.strings[5].noteName}</td>
			<td class="harmony">{chord.strings[5].harmony}</td>
		</tr>
		
	</table>
	<p class="chord-name">{chord.chordName}</p>
	<p class="chord-function">{chord.harmonicFunction}</p>
		
</div>

</div>

<style>
* {
	margin: 0;
	padding: 0;
}

.grid-card {
	/* border: solid 1px salmon; */
	max-width: 150px;
	display: flex;
	flex-direction: column;
	align-items: center;
}

.chord-grid {
	/* border: solid 1px salmon; */
}

.chord-grid td  {
	/* border: solid 1px salmon; */
	width: 2em;
	padding: 0;
	margin: 0;
	text-align: center;
	line-height: 1;

}


.frets {
	font-weight: bold;
}
.notes {
	font-style: italic;
}
.chord-name {
	font-size: 1.2rem;
	font-weight: bold;
	margin: 0;
}

li {
	display: inline-block;

}

ul {padding: .5em .2em;}
</style>