<script lang="ts">

import { getMode, makeMusicalSpectre, makeChord, makeGuitarString }  from './Functions.svelte'
import {tuning, chromaticScales} from './Constants.svelte'
import HarmonyGrid from './HarmonyGrid.svelte'





 let majorScales = {
	 C: ["c", "d", "e", "f", "g", "a", "b"],
	 G: [ "g", "a", "b","c", "d", "e", "f#"],
	 D: [ "d", "e", "f#", "g", "a", "b", "c#"],
	 A: [ "a", "b", "c#", "d", "e", "f#", "g"],
	 E: [ "e", "f#", "g", "a", "b", "c#", "d"] 
	
 }
 
function makeGuitarNeck(tuning: string[], frets: number) {
   return tuning.map(note => makeGuitarString(note, frets + 1))
}


 
let guitarneck = makeGuitarNeck(tuning.regular, 21)
// console.log(guitarneck)






 

// let aMinor = new GuitarChord("Am", "A natural minor", "i", chord.scale, chord.strings)
// console.log(aMinor)
</script>

<h1>Guitar neck</h1>
<table>
{#each guitarneck as fretboard, i }

	 <tr id="string{i + 1}">
	{#each fretboard as notes }
	<td class="string-names">{i + 1} str</td>
		{#each notes as note}
	
		<td class="{note}">{note}</td>

		{/each}
	{/each}
	</tr>

	
{/each}
</table>
<h1>Harmony</h1>
<div class="chordsheet">
	<HarmonyGrid/> <HarmonyGrid/>
</div>


<style>
	 * {padding: 0;}

	table td {
		padding: 5px 7px;
		text-align: center;
		background-color: antiquewhite;
	}

	.chordsheet {
		display: flex;
		flex-direction: row;
	}

	.string-names {
		background-color: rgb(148, 141, 141);
	}
	.c3 {
		background-color: aqua;
	}

	.e3 {
		background-color: orange;
	}

	.g2 {background-color: blueviolet;}
</style>