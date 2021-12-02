<script lang="ts" context="module">
import {makeGuitarNeck} from './Functions.svelte'
import {tuning} from './Constants.svelte'

export const frets = 21
export const flats = false

export const guitarNeck = makeGuitarNeck(tuning.regular, frets, flats)

export const theArray = []

</script>



<h1>Guitar neck</h1>
<table>
  {#each guitarNeck as fretboard, i }

	 <tr id="string{i + 1}">
	{#each fretboard as notes }
	<td class="string-names">{i + 1} str</td>
		{#each notes as note}
	
		<td class={note}>{note}</td>

		{/each}
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
</style>






