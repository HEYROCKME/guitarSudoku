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

<h1>Guitar neck</h1>
<table>
  {#each guitarNeck as fretboard, i }
    <tr>{#each fretboard as note}
        <td class={note.classCSS}>{note.noteName}</td>
      {/each}
    </tr>
  {/each}
</table>

<style>
  * {padding: 0;}

 table td {
   padding: 5px 7px;
   text-align: center;
   background-color: antiquewhite;
 }


 .string-names {
   background-color: rgb(148, 141, 141);
 }
 .c3 {
   background-color: aqua;
 }

 .e3 {
   background-color: orange;
 }

 .g2 {background-color: blueviolet;}

 .pink {background-color: pink;}
 .skyblue {background-color: skyblue;}
 .lightgreen {background-color: lightgreen;}
 .sandybrown {background-color: sandybrown;}
 .aquamarine {background-color: aquamarine;}
 .goldenrod {background-color: goldenrod;}
</style>






