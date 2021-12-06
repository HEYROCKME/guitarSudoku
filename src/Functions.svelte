<script lang="ts" context="module">
import { element } from 'svelte/internal';

import App from './App.svelte';

import Constants, {chromaticScales, chromaticFullRangeSharps, chromaticFullRangeFlats} from './Constants.svelte'
import GuitarNeck from './GuitarNeck.svelte';
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
  
  return flippedNotes
  
} 

// Takes Scales and Transposes to all all octaves
export function makeMusicalSpectre(scale: string[]  ) {
  let octaves = [ 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 ]
  let fullChromatic = []
  
  octaves.map( octave => {
    scale.map(note => {
    fullChromatic.push(note + octaves[octave])})
	})
	// console.log(fullChromatic)
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


//full single string from notean number of frets... Takes note name (string) in e.g "e3" and number of frets (number)

export function makeGuitarString(tunedTo : string,  frets: number, accidentals : boolean ) {
	let stringArea = !accidentals ? chromaticFullRangeSharps :  chromaticFullRangeFlats
	let openFret = stringArea.indexOf(tunedTo)
	let guitarString = stringArea.slice(openFret, openFret + frets)
			
	let result =[]

	guitarString.map((element : string, i : number) => { 
		

			let note = {
				noteName: element,
				note: element.length <= 2 ? element[0] : element[0] + "#",
				fret: i,
				classCSS: !element.includes("#") ? element : element[0] + "sharp" + element[2] ,

			}	
			
			result.push(note)
		

	})
	
    return result

}


export function makeGuitarNeck(tuning: string[], frets: number, flats : boolean) {
 let neck =  tuning.map(guitarString => makeGuitarString(guitarString, frets +1, flats))
//  let neckObject = {
// 	 string1: neck[0],
// 	 string2: neck[1],
// 	 string3: neck[2],
// 	 string4: neck[3],
// 	 string5: neck[4],
// 	 string6: neck[5],
	 
//  }

	

//  return neckObject
 return neck
}


</script>

