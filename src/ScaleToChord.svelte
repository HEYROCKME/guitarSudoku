<script lang="ts" context="module">

// import {getMode} from './Functions.svelte'
// import { chromaticScales } from "./Constants.svelte";

let regex = /[a-z][b]\b/g

const scaleRecipies = {
    major: [1, 3, 5, 6, 8, 10, 12],
    minor: [1, 3, 4, 6, 8, 9, 11]
}


export function makeScale(chromatics : string[], scaleType: string) {
    let scale = []
    if (scaleType === "major") {
        scaleRecipies.major.forEach(step => scale.push(chromatics[step -1]))    
    } else {
        scaleRecipies.minor.forEach(step => scale.push(chromatics[step -1]))
    }
    
   let newScale = scale.map((item) => 
   {return item.replace(regex, item[0] + "♭" )} )

    // console.log(newScale);
    
    return newScale

}

// let cMajor = makeScale(chromaticScales.flats, "major")
// let cMinor = makeScale(chromaticScales.flats, "major")
// let fMinor = makeScale(getMode(chromaticScales.sharps, 6), "minor")

// let chromatic = getMode(chromaticScales.sharps, 6)
// let fLydian = getMode(cMajor, 4)
 


// function makeMajor(note) {


// }


</script>
<!-- <h1>Generated scales</h1>
<p>C Major: {cMajor}</p>
<p>C minor: {cMinor}</p>
<p>chromatic {chromatic}</p>
<p>F lydian mode: {fLydian}</p>
<p>F minor: {fMinor}</p> -->