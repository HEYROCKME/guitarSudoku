<script lang="ts" context="module">
import {makeGuitarNeck} from './Functions.svelte'
import {tuning} from './Constants.svelte'
import { flats } from './stores'
let accidentals : boolean

flats.subscribe(value => {
  accidentals = value
})
flats.set(false)


export const frets = 21
export const guitarNeck = makeGuitarNeck(tuning.regular, frets, accidentals)
</script>