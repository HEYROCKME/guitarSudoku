
<script lang="ts" context="module">
import {makeMusicalSpectre } from '../Functions.svelte'
import {chromaticScales } from '../Constants.svelte'

export const chromaticFullRangeSharps = makeMusicalSpectre(chromaticScales.sharps)
export const chromaticFullRangeFlats = makeMusicalSpectre(chromaticScales.flats)

</script>

