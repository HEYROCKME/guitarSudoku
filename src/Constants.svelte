<script context="module" lang="ts">
	
    

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




let majorScales = {
	 C: ["c", "d", "e", "f", "g", "a", "b"],
	 G: [ "g", "a", "b","c", "d", "e", "f#"],
	 D: [ "d", "e", "f#", "g", "a", "b", "c#"],
	 A: [ "a", "b", "c#", "d", "e", "f#", "g"],
	 E: [ "e", "f#", "g", "a", "b", "c#", "d"] 
	
 }


// ScaleToChord Component 

//Flats regex
export const regexFindFlats = /[a-z][b]\b/g

export const scaleRecipies = {
    major: [1, 3, 5, 6, 8, 10, 12],
    minor: [1, 3, 4, 6, 8, 9, 11],
	minor_melodic: [1, 2, 4, 6, 8, 10, 12],
	minor_harmonic: [1, 2, 4, 6, 8, 9, 12]
}

</script>