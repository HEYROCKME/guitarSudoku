<script context="module" lang="ts">
    

	// Spread a scale over full spectre
function makeMusicalSpectre(scale: string[]  ) {
  let octaves = [ 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 ]
  let fullChromatic = []

  octaves.map( octave => {
    scale.map(note => {
      fullChromatic.push(note + octaves[octave])})
	  })
	
  return fullChromatic
}

// ROMAN Numerals
export const romanNumerals = {
	  upperCaseTwelveTone: [ "I", "(b)II", "II","(b)III", "III", "IV", "(b)V", "V", "(b)VI", "VI", "(b)VII", "VII" ],
	  lowerCaseTwelveTone: [ "i", "(b)ii", "ii", "(b)iii", "iii", "iv", "(b)v", "v", "(b)vi", "vi", "(b)vii", "vii" ],
	  majorScale: ["I", "ii", "iii", "IV", "V", "vi", "vii(b5)"],
	  minorScale: ["i", "iib5", "III", "iv", "v", "(b)VI", "(b)VII"]
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