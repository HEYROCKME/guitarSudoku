<script context="module" lang="ts">
    import {makeMusicalSpectre} from "./Functions.svelte";
//Chromatic scales
export const chromaticScales ={
	sharps: ["c", "c#", "d", "d#", "e", "f", "f#", "g", "g#", "a","a#","b"],
	flats: ["c", "db", "d", "eb", "e", "f", "gb", "g", "ab", "a","bb","b"]
}

export const tuning = {
    regular: ['e3', 'b2', 'g2', 'd2', 'a1', 'e1'],
    dropD: ['e3', 'b3', 'g2', 'd2', 'a1', 'd1']
}


export const chromaticFullRangeSharps = makeMusicalSpectre(chromaticScales.sharps)
export const chromaticFullRangeFlats = makeMusicalSpectre(chromaticScales.flats)
</script>