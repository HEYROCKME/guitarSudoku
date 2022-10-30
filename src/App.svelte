<script lang="ts">
import HarmonyGrid from './HarmonyGrid.svelte'
import GuitarNeck from './GuitarNeck.svelte'
import DiatonicHarmony from './DiatonicHarmony.svelte';
import MakeScale from './MakeScale.svelte'

</script>


<header>
	<h1>Guitar Sudoku Tools V0.01a</h1>
	<p>
		<span id="intro">Guitar Sudoku Tools aims to be a code library that generates guitar lessons material APIs related to the Guitar Sudoku method.</span>
	</p>
</header>

<main>





<MakeScale noteName="e" scaleType="major" />
<MakeScale noteName="d" scaleType="minor_melodic"/>
<DiatonicHarmony />
 
<section id="guitarneck">

	<GuitarNeck />
</section>


<h2>Harmony</h2>
<div class="chordsheet">
	<HarmonyGrid chordName="E" 
	strings =  {[
          {openString: "e", stringNum: 1, fret: "0", noteName: "e", harmony: "r", note: "e3"},
          {openString: "b", stringNum: 2, fret: "0", noteName: "b", harmony: "5", note: "b2"},
          {openString: "g", stringNum: 3, fret: "0", noteName: "g", harmony: "b3", note:"g2" },
          {openString: "d", stringNum: 4, fret: "2", noteName: "e", harmony: "r",  note:"e2"},
          {openString: "a", stringNum: 5, fret: "2", noteName: "b", harmony: "5", note: "b1"},
          {openString: "e", stringNum: 6, fret: "0", noteName: "e", harmony: "r", note: "e1"}
                      ]}
	/> 
	<HarmonyGrid  chordName="Am"/>
	
</div>

</main>

<footer>
	<p>
		made by <a href="https://grafisker.no">HEYROCKME|Grafisker</a> 
	</p>
	  
</footer>


<style>



	 * {padding: 0;}

	/* .selectors {
		display: flex;
		flex-direction: row;
	} */

	.chordsheet {
		display: flex;
		flex-direction: row;
	}


 header {
	padding: 3em;
	margin: 0 auto;
	width: 80vw;
	
 }
 header p {
	width: 50vw;
 }

 main {
	margin: 0 auto;
	width: 80vw;
 }

 footer {
	padding: 3em;
	margin: 0 auto;
	width: 50vw;
	text-align: center;
 }
	
</style>