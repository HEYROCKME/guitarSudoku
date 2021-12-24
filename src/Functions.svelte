<script lang="ts" context="module">
import {chromaticFullRangeSharps, chromaticFullRangeFlats} from './Constants/Scales.svelte'
import {regexFindFlats, scaleRecipies} from './Constants.svelte'
import { flats } from './stores'

let accidentals : boolean

flats.subscribe(value => {
	accidentals = value
})

  //turns scale into mode
export function getMode( scale: string[], scaleDegree: number) {
  let mode = []
  let notes = scale.slice(0,scaleDegree - 1)
  let flippedNotes = scale.slice(- scale.length + (scaleDegree - 1))
  mode = notes.map(note => {flippedNotes.push(note)})
//   console.log(flippedNotes)
  return flippedNotes
  
} 

// Makes a ten octave span of notes

export function makeMusicalSpectre(scale: string[]  ) {
  let octaves = [ 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 ]
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
	return scaleInThids.concat(upperExtensions).slice(0, notes)
}

// // Generate Full single string from note and number of frets... 
// // Takes note name (string) in e.g "e3" and number of frets (number)

export function makeGuitarString(tunedTo : string,  frets: number, accidentals : boolean ) {
	let stringArea = !accidentals ? chromaticFullRangeSharps :  chromaticFullRangeFlats
	let openFret = stringArea.indexOf(tunedTo)
	let guitarString = stringArea.slice(openFret, openFret + frets)
			
	let result = []

	guitarString.map((element : string, i : number) => { 
			let note = {
				noteName: element,
				note: element.length <= 2 ? element[0] : element[0] + "#",
				fret: i,
				classCSS: !element.includes("#") ? element : element[0] + "sharp" + element[2],
			}	
			result.push(note)		
	})
    return result
}

//Makes full guitar from tuning, frets and flats
export function makeGuitarNeck(tuning: string[], frets: number, flats : boolean) {
 let neck =  tuning.map(guitarString => makeGuitarString(guitarString, frets +1, flats))
 return neck
}

// MAKE DIATONIC CHORDS

export function makeDiatonicChords(scale : string[], notesInChord : number ) {
  let diatonicChords = []
  scale.map((note, index, array) => { 
    let chord = makeChord(getMode(scale, index + 1 ), notesInChord)
	diatonicChords.push(chord)
})

return diatonicChords


}

export function makeScale(chromatics : string[], scaleType: string) {
    let scale = []
    if (scaleType === "major") {
        scaleRecipies.major.forEach(step => scale.push(chromatics[step -1]))    
    } else {
        scaleRecipies.minor.forEach(step => scale.push(chromatics[step -1]))
    }
    
   let newScale = scale.map((item) => 
   {return item.replace(regexFindFlats, item[0] + "♭" )} )

    // console.log(newScale);
    
    return newScale

}

</script>

