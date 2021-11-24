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
 
 
 
console.log(
	makeGuitarString( "e3", 21),
	makeGuitarString( "b2", 21),
	makeGuitarString( "g2", 21),
	makeGuitarString( "d2", 21),
	makeGuitarString( "a2", 21),
	makeGuitarString( "e1", 21)
)






 

// let aMinor = new GuitarChord("Am", "A natural minor", "i", chord.scale, chord.strings)
// console.log(aMinor)
</script>

<HarmonyGrid/>