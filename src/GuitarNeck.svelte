<script lang="ts" >
  import  { guitarNeck, frets } from './NeckMaker.svelte'

  const noteRegex = /\b([a-g]{1}\d{1})|([a-g](sharp)\d{1})\b/gi 
  const colorRegex = /\w+$/
  let displayFrets = []
  let fretCount = 0
  let colors = [ "pink", "salmon", "skyblue", "lightgreen",
  "sandybrown","aquamarine", "goldenrod"] 
  let classCount = 0

  while (fretCount < frets +1) {
    displayFrets.push(fretCount)
    fretCount +=1
  }

const handleClick = (e) => {
    let classEvent = e.target.className
    let lastClass =  e.target.className.match(colorRegex).toString()
    let noteClass = "." + classEvent.match(noteRegex).toString()
    let classCollected = document.querySelectorAll(noteClass)
     
    if (colors.includes(lastClass)) {
          classCollected.forEach(item => {
          item.classList.remove(lastClass)})
           classCount--   
    }else {
        classCollected.forEach(item => item.classList.add(colors[classCount]))
        classCount+=1
      }  
}

</script>

<h2>Guitar neck</h2>
<table>
  {#each guitarNeck as fretboard, i }
  
  <tr>
      <td class="utility">string{i+1}</td>
   
   {#each fretboard as note}
        <td 
        class="fretted-note fretboard {note.classCSS} fret{note.fret}"
        on:click={handleClick}
        >  {note.noteName}</td>
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

 .fretboard:hover {
background-color: rgb(224, 206, 105);

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
   font-size: .5rem;
 }

 .string-names {
   background-color: rgb(148, 141, 141);
 }

 .fretted-note {
  font-size: .8rem;
 }
 
 .pink {background-color: pink;}
.salmon {background-color: salmon;}
 .skyblue {background-color: skyblue;}
 .lightgreen {background-color: lightgreen;}
 .sandybrown {background-color: sandybrown;}
 .aquamarine {background-color: aquamarine;}
 .goldenrod {background-color: goldenrod;}


 
</style>






