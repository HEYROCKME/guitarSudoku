<script context="module" lang="ts">
    
    function makeMusicalSpectre(scale: string[]  ) {
  let octaves = [ 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 ]
  let fullChromatic = []
  
  octaves.map( octave => {
    scale.map(note => {
    fullChromatic.push(note + octaves[octave])})
	})
	// console.log(fullChromatic)
	return fullChromatic
}

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

let majorScales = {
	 C: ["c", "d", "e", "f", "g", "a", "b"],
	 G: [ "g", "a", "b","c", "d", "e", "f#"],
	 D: [ "d", "e", "f#", "g", "a", "b", "c#"],
	 A: [ "a", "b", "c#", "d", "e", "f#", "g"],
	 E: [ "e", "f#", "g", "a", "b", "c#", "d"] 
	
 }
</script>