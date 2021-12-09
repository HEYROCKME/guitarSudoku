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
      <td class="utility">string{i+1}</td>
   
   {#each fretboard as note}
        <td class="{note.classCSS} fret{note.fret}">{note.noteName}</td>
      {/each}
    </tr>
  {/each}
  <tr>
    <td class="utility">frets</td>
    {#each displayFrets as frets, i}
    <td class="utility">{i}</td>
    {/each}
  </tr>
</table>

<style>
  * {padding: 0;}

 table td {
   padding: 4px 7px;
   text-align: center;
   background-color: antiquewhite;
 }

 .fret0 {
   background-color: rgb(236, 223, 206);
 }
 .fret1 {
   min-width: 40px;
 } 
 .fret2 {
    min-width: 39px; 
  } 

 .fret3 {
   min-width: 38px;
 } 
 .fret4 {
   min-width: 37px;
 } 
 .fret5 {
   min-width: 36px;
 } 
 .fret6 {
   min-width: 35px;
 } 
 .fret7 {
   min-width: 34px;
 } 
 .fret8 {
   min-width: 33px;
 } 
 .fret9 {
   min-width: 32px;
 } 
 .fret10 {
   min-width: 31px;
   
 } 
 .fret11 {
   min-width: 30px;
 } 
 .fret12 {
   min-width: 29px;
 } 
 .fret13 {
   min-width: 28px;
 } 
 .fret14 {
   min-width: 27px;
 } 
 .fret15 {
   min-width: 26px;
 } 
 .fret16 {
   min-width: 25px;
 } 
 .fret17 {
   min-width: 24px;
 }

 .fret18 {
   min-width: 23px;
 } 
 .fret19 {
   min-width: 22px;
 } 
 .fret20 {
   min-width: 21px;
 } 
 .fret21 {
   min-width: 20px;
 } 
 

 .utility {
   background-color: transparent;
   font-size: .8rem;
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






