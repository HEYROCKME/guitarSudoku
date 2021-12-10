<script lang="ts">
import App from "./App.svelte";

import { chromaticScales } from "./Constants.svelte";

let regex = /[a-z][b]\b/g

const scaleRecipies = {
    major: [1, 3, 5, 6, 8, 10, 12],
    minor: [1, 3, 4, 6, 8, 9, 11]
}


function makeScale(string) {
    let scale = []
  
    if (string === "major") {
        scaleRecipies.major.forEach(step => scale.push(chromaticScales.flats[step -1]))
        
    } else {
        scaleRecipies.minor.forEach(step => scale.push(chromaticScales.flats[step -1]))}
    
   
   
    

   let newScale = scale.map((item) => 
   {return item.replace(regex, item[0] + "♭" )} )

    console.log(newScale);
    
    return newScale


 



}

let Cmajor = makeScale("major")
let Cminor = makeScale("minor")

 


// function makeMajor(note) {


// }


</script>

<p>C Major: {Cmajor}</p>
<p>C minor: {Cminor}</p>