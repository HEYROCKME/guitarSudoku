<script lang="ts" context="module">
  //turns scale into mode
  export function getMode( scale: string[], scaleDegree: number) {
	let mode = []
	let notes = scale.slice(0,scaleDegree - 1)
    let flippedNotes = scale.slice(- scale.length + (scaleDegree - 1))
    mode = notes.map(note => {flippedNotes.push(note)})

    return flippedNotes
} 

// Takes Scales and Transposes to all all octaves
export function makeMusicalSpectre(scale: string[]) {
  let octaves= [ 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 ]
  let fullChromatic = []
	octaves.map( octave => {
    	scale.map(note => {
    	fullChromatic.push(note + octaves[octave])})
	})
	return fullChromatic
}

// Takes a scale and stacks it into chords (tones by thids)
export function makeChord(scale : string[], notes : number ) {
	let scaleInThids = []
	let upperExtensions = []
	scale.filter((note, index, array) => {
		if (index % 2 === 0) {
			scaleInThids.push(note)
		} else upperExtensions.push(note) 
	})
	return scaleInThids.concat(upperExtensions).splice(0, notes)
}




</script>

