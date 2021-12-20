<script lang="ts">
import HarmonyGrid from './HarmonyGrid.svelte'
import GuitarNeck from './GuitarNeck.svelte'
import DiatonicHarmony from './DiatonicHarmony.svelte';
import MakeScale from './MakeScale.svelte'

</script>

<h1>Guitar Sudoku</h1>

<MakeScale noteName="e" scaleType="major" />
<DiatonicHarmony />
<GuitarNeck />


<h1>Harmony</h1>
<div class="chordsheet">
	<HarmonyGrid chordName="Em" 
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


	
</style>