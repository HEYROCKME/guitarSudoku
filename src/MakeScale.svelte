<script lang="ts">
import {makeScale, getMode} from './Functions.svelte'
import {chromaticScales} from './Constants.svelte'

// export let noteName : string
// export let scaleType : string

let cMajor = makeScale(chromaticScales.flats, "major")
let cMinor = makeScale(chromaticScales.flats, "major")
let fMinor = makeScale(getMode(chromaticScales.flats, 6), "minor")

let chromatic = getMode(chromaticScales.sharps, 6)
let fLydian = getMode(cMajor, 4)



</script>


<h1>Guitar Sudoku</h1>

<h2>the makeScale() function</h2>

<p>C Major: {cMajor}</p>
<p>C minor: {cMinor}</p>
<p>chromatic {chromatic}</p>
<p>F lydian mode: {fLydian}</p>
<p>F minor: {fMinor}</p> 







