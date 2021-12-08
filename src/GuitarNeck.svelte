<script lang="ts" >
  import  { guitarNeck, frets } from './NeckMaker.svelte'

  let displayFrets = []
  let fretCount = 0

  while (fretCount < frets +1) {
    displayFrets.push(fretCount)
    fretCount +=1
  }

</script>

<h1>Guitar neck</h1>
<table>
  {#each guitarNeck as fretboard, i }
  
  <tr>
      <td>string{i+1}</td>
   
   {#each fretboard as note}
        <td class={note.classCSS}>{note.noteName}</td>
      {/each}
    </tr>
  {/each}
  <tr>
    <td></td>
    {#each displayFrets as frets, i}
    <td>{i}</td>
    {/each}
  </tr>
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
 
 .pink {background-color: pink;}
.salmon {background-color: salmon;}
 .skyblue {background-color: skyblue;}
 .lightgreen {background-color: lightgreen;}
 .sandybrown {background-color: sandybrown;}
 .aquamarine {background-color: aquamarine;}
 .goldenrod {background-color: goldenrod;}
</style>






