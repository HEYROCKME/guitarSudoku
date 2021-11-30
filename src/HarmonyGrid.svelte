<script type="module" lang="ts">
 
    const chord = { 
    chordName: "Am", 
    chordKey: "A-minor (natural)",
    chordTones: ["a", "c", "e"], 
    harmonicFunction: "i",
    scale: ["a", "b", "c", "d", "e", "f", "g"],
    diatonicChords: ["i", "iib5", "III", "iv", "v", "bVI", "bVII" ],
    strings: [
          {openString: "e", stringNum: 1, fret: "0", noteName: "e", harmony: "5", note: "e3"},
          {openString: "b", stringNum: 2, fret: "1", noteName: "c", harmony: "b3", note: "c3"},
          {openString: "g", stringNum: 3, fret: "2", noteName: "a", harmony: "r", note:"a2" },
          {openString: "d", stringNum: 4, fret: "2", noteName: "e", harmony: "5",  note:"e2"},
          {openString: "a", stringNum: 5, fret: "0", noteName: "a", harmony: "r", note: "a1"},
          {openString: "e", stringNum: 6, fret: "x", noteName: "-", harmony: "-", note: ""}
                      ]
      }
  
  class GuitarChord {
      chordName : string
      chordKey  : string
      harmonicFunction : string
      strings : {}[]
      scale : string[]
  
  
  
      constructor(chordName, chordKey, harmonicFunction, scale, strings ) {
          this.chordName = chordName
          this.chordKey = chordKey
          this.harmonicFunction = harmonicFunction
          this.strings = strings
          this.scale = scale
          
  
      }
  }


 



</script>



<!-- <h2>Harmony Grid</h2> -->
<div class="card">
 
	<!-- <p class="key">Key: {chord.chordKey}</p> -->

	<div class="grid-card">
  	  
	  <table class="chord-grid">
		<tr>
			<td class="frets">{chord.strings[0].fret}</td>
			<td class="notes">{chord.strings[0].noteName}</td>
			<td class="harmony">{chord.strings[0].harmony}</td>
		</tr>
		<tr>
			<td class="frets">{chord.strings[1].fret}</td>
			<td class="notes">{chord.strings[1].noteName}</td>
			<td class="harmony">{chord.strings[1].harmony}</td>
		</tr>
		<tr>
			<td class="frets">{chord.strings[2].fret}</td>
			<td class="notes">{chord.strings[2].noteName}</td>
			<td class="harmony">{chord.strings[2].harmony}</td>
		</tr>
		<tr>
			<td class="frets">{chord.strings[3].fret}</td>
			<td class="notes">{chord.strings[3].noteName}</td>
			<td class="harmony">{chord.strings[3].harmony}</td>
		</tr>
		<tr>
			<td class="frets">{chord.strings[4].fret}</td>
			<td class="notes">{chord.strings[4].noteName}</td>
			<td class="harmony">{chord.strings[4].harmony}</td>
		</tr>
		<tr>
			<td class="frets">{chord.strings[5].fret}</td>
			<td class="notes">{chord.strings[5].noteName}</td>
			<td class="harmony">{chord.strings[5].harmony}</td>
		</tr>
		
	</table>
	<p class="chord-name">{chord.chordName}</p>
	<p class="chord-function">{chord.harmonicFunction}</p>
		
</div>

</div>

<style>
* {
	margin: 0;
	padding: 0;
}

.grid-card {
	/* border: solid 1px salmon; */
	max-width: 150px;
	display: flex;
	flex-direction: column;
	align-items: center;
}

.chord-grid {
	/* border: solid 1px salmon; */
    padding: .75em;
}

.chord-grid td  {
	/* border: solid 1px salmon; */
	width: 2em;
	padding: 0;
	margin: 0;
	text-align: center;
	line-height: 1;

}


.frets {
	font-weight: bold;
}
.notes {
	font-style: italic;
}

.harmony {
    color: rgb(138, 130, 130);
    
}
.chord-name {
	font-size: 1.2rem;
	font-weight: bold;
	margin: 0;
}


</style>

