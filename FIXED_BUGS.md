# Fixed bugs

Bugs in music21 found while porting it to Rust in
[music21-rs](https://github.com/float3/music21-rs), each held to music21 by
a parity test, and fixed here.

`master` is cuthbertLab/music21 `master` with every fix below merged in.
Each fix also stands alone on its own branch, `pr/<name>`, one commit off
upstream `master` with a regression test that fails without it, ready to be
sent upstream; those branches never carry this file. Where `master` holds a
fix in an earlier form than its branch, the branch is the one to send.

## Merged upstream

- [#2003](https://github.com/cuthbertLab/music21/pull/2003) a malformed ratio in the Scala archive's `sparschuh-stanhope.scl`
- [#2026](https://github.com/cuthbertLab/music21/pull/2026) Scala files with text after a pitch value
- [#2027](https://github.com/cuthbertLab/music21/pull/2027) `removeRedundantPitches` taking a negative octave for a flat
- [#2028](https://github.com/cuthbertLab/music21/pull/2028) `getPitchFromNodeDegree` handing back a pitch the scale's cache owns
- [#2038](https://github.com/cuthbertLab/music21/pull/2038) `OctaveRepeatingScale` appending to the list of steps it was given
- [#2043](https://github.com/cuthbertLab/music21/pull/2043) a descending realization checking its range against the unaltered pitch
- [#2044](https://github.com/cuthbertLab/music21/pull/2044) `derive` leaving out a scale's altered degrees
- [#2045](https://github.com/cuthbertLab/music21/pull/2045) an octave-repeating scale wider than an octave starting an octave off
- [#2046](https://github.com/cuthbertLab/music21/pull/2046) timespan offsets added as floats
- [#2048](https://github.com/cuthbertLab/music21/pull/2048) two needless deepcopies in `AbstractScale`
- [#2054](https://github.com/cuthbertLab/music21/pull/2054) a realization cached without its altered degrees
- [#2056](https://github.com/cuthbertLab/music21/pull/2056) `getAllNamesForInstrument` finding names only for some instruments
- [#2057](https://github.com/cuthbertLab/music21/pull/2057) `nextPitch` on a cyclical network answering below the pitch given
- [#2110](https://github.com/cuthbertLab/music21/pull/2110) a missing comma that merged the NoteWorthy tenor and percussion clef names
- [#2111](https://github.com/cuthbertLab/music21/pull/2111) MusicXML export failing on an arpeggio mark over a single note
- [#2112](https://github.com/cuthbertLab/music21/pull/2112) an empty `TimespanTree` yielding a verticality at `-inf`
- [#2113](https://github.com/cuthbertLab/music21/pull/2113) `extractorsById(library='all')` leaving out the native extractors
- [#2114](https://github.com/cuthbertLab/music21/pull/2114) a one-offset search missing a float slightly off an element's fractional offset
- [#2115](https://github.com/cuthbertLab/music21/pull/2115) pitch detection without scipy overflowing on sixteen-bit samples
- [#2116](https://github.com/cuthbertLab/music21/pull/2116) a metadata search failing on a query that will not compile as a regular expression
- [#2117](https://github.com/cuthbertLab/music21/pull/2117) the complement of an empty residual class in sieve
- [#2118](https://github.com/cuthbertLab/music21/pull/2118) a stage-1 MuseData part getting a name it does not have
- [#2119](https://github.com/cuthbertLab/music21/pull/2119) MuseData files with Windows line endings keeping a carriage return on every line
- [#2120](https://github.com/cuthbertLab/music21/pull/2120) path doctests failing on Windows
- [#2121](https://github.com/cuthbertLab/music21/pull/2121) `ScoreReduction` failing on a lone part
- [#2122](https://github.com/cuthbertLab/music21/pull/2122) a Humdrum spine split a second time being dropped
- [#2123](https://github.com/cuthbertLab/music21/pull/2123) Capella single barlines failing to import and prolonged tuplets read as 3:2
- [#2124](https://github.com/cuthbertLab/music21/pull/2124) `ChordBassMotionFeature` failing on a `NoChord`
- [#2125](https://github.com/cuthbertLab/music21/pull/2125) an ABC measure's overflow being lost when no time signature fits it
- [#2127](https://github.com/cuthbertLab/music21/pull/2127) a `ReductiveNote` on a chord looking for a C instead of taking its highest note
- [#2128](https://github.com/cuthbertLab/music21/pull/2128) tuplets set on a duration that had not worked out its own components being lost
- [#2129](https://github.com/cuthbertLab/music21/pull/2129) `PartReduction` lengthening the score's own dynamics
- [#2130](https://github.com/cuthbertLab/music21/pull/2130) TinyNotation `}` closing a tie instead of its bracket, and states counting time signatures as notes
- [#2132](https://github.com/cuthbertLab/music21/pull/2132) a trill with an accidental exporting no `accidental-mark`
- [#2133](https://github.com/cuthbertLab/music21/pull/2133) `beatAndMeasureFromOffset` counting a split measure's second half in the wrong meter
- [#2134](https://github.com/cuthbertLab/music21/pull/2134) a split measure's right barline becoming its second half's left barline
- [#2136](https://github.com/cuthbertLab/music21/pull/2136) `mostCommonMeasureRhythms` failing on chords and unpitched notes
- [#2137](https://github.com/cuthbertLab/music21/pull/2137) an octave-repeating scale closing with a zero-width step
- [#2138](https://github.com/cuthbertLab/music21/pull/2138) figured-bass realizations sharing pitch objects
- [#2126](https://github.com/cuthbertLab/music21/pull/2126) a chord exported to MusicXML sorted on a copy that was then discarded
- [#2140](https://github.com/cuthbertLab/music21/pull/2140) harmonic minor built through altered degrees
- [#2141](https://github.com/cuthbertLab/music21/pull/2141) volpiano breaks and neumes put in the wrong measure
- [#2142](https://github.com/cuthbertLab/music21/pull/2142) `makeTies` adding the measure it makes once per voice
- [#2145](https://github.com/cuthbertLab/music21/pull/2145) `os.getuid` reported by mypy and pylint on Windows
- [#2144](https://github.com/cuthbertLab/music21/pull/2144) makeTies: keep voices tied into a measure without voices
- [#2147](https://github.com/cuthbertLab/music21/pull/2147) Fix the binary_dots entry for braille dots 1-2-3-5-6
- [#2148](https://github.com/cuthbertLab/music21/pull/2148) Make BrailleText.showHand store the hand and set only its symbol
- [#2149](https://github.com/cuthbertLab/music21/pull/2149) Detect hidden tuplet numbers in braille noteToBraille
- [#2150](https://github.com/cuthbertLab/music21/pull/2150) Transcribe a note after an empty TextExpression in braille
- [#2151](https://github.com/cuthbertLab/music21/pull/2151) Read the left-hand key in a keyboard segment heading
- [#2152](https://github.com/cuthbertLab/music21/pull/2152) Convert forbiddenChords in ChordReducer.run
- [#2153](https://github.com/cuthbertLab/music21/pull/2153) lily: quote note colours with quoteString
- [#2154](https://github.com/cuthbertLab/music21/pull/2154) Allow adjacentAverage windowed analysis with windows above size one
- [#2155](https://github.com/cuthbertLab/music21/pull/2155) Find nextPitch neighbors on cycles wider than an octave
- [#2159](https://github.com/cuthbertLab/music21/pull/2159) Analyze modal keys in QualityFeature
- [#2160](https://github.com/cuthbertLab/music21/pull/2160) Fix findConsecutiveNotes(skipUnisons=True) on repeated notes and chords
- [#2162](https://github.com/cuthbertLab/music21/pull/2162) Realize figured-bass lines holding tuplets
- [#2163](https://github.com/cuthbertLab/music21/pull/2163) Keep the stretch before a span's first dynamic in PartReduction
- [#2165](https://github.com/cuthbertLab/music21/pull/2165) Count ChordBassMotionFeature motion upward
- [#2166](https://github.com/cuthbertLab/music21/pull/2166) Place melodicIntervals at offsets in the stream analysed
- [#2168](https://github.com/cuthbertLab/music21/pull/2168) Smooth floating key analysis with each neighbour's own interpretations

## Fixed here, not yet upstream

### Streams

- [`pr/measures-collect-priority`](https://github.com/float3/music21/tree/pr/measures-collect-priority): Change a collected object's priority in Stream.measures only when needed (open: [#2172](https://github.com/cuthbertLab/music21/pull/2172))
- [`pr/split-measure-time-signature`](https://github.com/float3/music21/tree/pr/split-measure-time-signature): Give a split measure's second half the clef, key and meter in force where it is split
- [`pr/greatest-divisor-grace-notes`](https://github.com/float3/music21/tree/pr/greatest-divisor-grace-notes): Slice by the greatest divisor past grace notes and empty measures
- [`pr/slice-at-offsets-voices`](https://github.com/float3/music21/tree/pr/slice-at-offsets-voices): Keep the pieces of a note cut in a voice in that voice
- [`pr/partstaff-measure-gap-2`](https://github.com/float3/music21/tree/pr/partstaff-measure-gap-2): Join PartStaffs after a measure missing from the first staff (open: [#2156](https://github.com/cuthbertLab/music21/pull/2156))

### Analysis and features

- [`pr/chord-reducer-hashable-timespans-2`](https://github.com/float3/music21/tree/pr/chord-reducer-hashable-timespans-2): Make ElementTimespan hashable (open: [#2169](https://github.com/cuthbertLab/music21/pull/2169))
- [`pr/chord-reducer-bass-gap-overlap`](https://github.com/float3/music21/tree/pr/chord-reducer-bass-gap-overlap): Keep fillBassGaps from overlapping a part's next timespan
- [`pr/chord-reducer-first-part-measures`](https://github.com/float3/music21/tree/pr/chord-reducer-first-part-measures): Chordify ChordReducer.run's reduction on the first part's measures
- [`pr/chord-reducer-pitch-class-key`](https://github.com/float3/music21/tree/pr/chord-reducer-pitch-class-key): Key ChordReducer weights by sorted pitch classes (open: [#2174](https://github.com/cuthbertLab/music21/pull/2174))
- [`pr/chord-reducer-old-measure-length`](https://github.com/float3/music21/tree/pr/chord-reducer-old-measure-length): Keep each measure's length in reduceChordsOld
- [`pr/chord-reducer-old-empty-measure`](https://github.com/float3/music21/tree/pr/chord-reducer-old-empty-measure): Reduce every measure in reduceChordsOld.multiPartReduction
- [`pr/partwise-trees-bulk-insert`](https://github.com/float3/music21/tree/pr/partwise-trees-bulk-insert): Insert each part's timespans at once in toPartwiseTimespanTrees (open: [#2173](https://github.com/cuthbertLab/music21/pull/2173))
- [`pr/chord-reducer-timespan-measures`](https://github.com/float3/music21/tree/pr/chord-reducer-timespan-measures): Choose ChordReducer.run's chords from slices of the score's timespans (design; issue first)
- [`pr/verticality-part-id-chord-notes`](https://github.com/float3/music21/tree/pr/verticality-part-id-chord-notes): Give chord notes part id groups in Verticality.makeElement
- [`pr/output-tab-orange-include-id`](https://github.com/float3/music21/tree/pr/output-tab-orange-include-id): Honor includeId and includeClassLabel in Orange and ARFF rows
- [`pr/features-as-list-rows`](https://github.com/float3/music21/tree/pr/features-as-list-rows): Return one row per instance from getFeaturesAsList
- [`pr/part-reduction-same-ids`](https://github.com/float3/music21/tree/pr/part-reduction-same-ids): Keep each part's spans apart in PartReduction when ids repeat
- [`pr/part-reduction-dynamic-on-barline-2`](https://github.com/float3/music21/tree/pr/part-reduction-dynamic-on-barline-2): Start each PartReduction span at the last dynamic before it (open: [#2171](https://github.com/cuthbertLab/music21/pull/2171))
- [`pr/part-reduction-average-weight`](https://github.com/float3/music21/tree/pr/part-reduction-average-weight): Average dynamics in PartReduction weights
- [`pr/part-reduction-whole-word-groups`](https://github.com/float3/music21/tree/pr/part-reduction-whole-word-groups): Match PartReduction part groups on whole words of the part id
- [`pr/dolan-part-groups`](https://github.com/float3/music21/tree/pr/dolan-part-groups): Set Dolan's default part groups when a stream is given

### Audio


### Scales and figured bass

- [`pr/relative-node-id-deterministic`](https://github.com/float3/music21/tree/pr/relative-node-id-deterministic): Choose among nodes sharing a pitch without randomness

### Formats

- [`pr/midi-deduplicate-instruments-2`](https://github.com/float3/music21/tree/pr/midi-deduplicate-instruments-2): Deduplicate instruments offset by offset (open: [#2158](https://github.com/cuthbertLab/music21/pull/2158))
- [`pr/nwctxt-chord-groups-2`](https://github.com/float3/music21/tree/pr/nwctxt-chord-groups-2): Read NWC Dur2/Pos2 chord notes and rest chords at the same offset (open: [#2139](https://github.com/cuthbertLab/music21/pull/2139))
- [`pr/nwc-binary-chords`](https://github.com/float3/music21/tree/pr/nwc-binary-chords): Read chord and rest-chord notes in binary NWC files
- [`pr/nwc-chord-dump`](https://github.com/float3/music21/tree/pr/nwc-chord-dump): Dump binary NWC chords as Dur2/Pos2 and rest chords as RestChord
- [`pr/romantext-high-numerals`](https://github.com/float3/music21/tree/pr/romantext-high-numerals): Reject roman numerals past VII
- [`pr/volpiano-end-breaks-layout`](https://github.com/float3/music21/tree/pr/volpiano-end-breaks-layout): Make volpiano breaks at the end of the text follow breaksToLayout
- [`pr/volpiano-neumes`](https://github.com/float3/music21/tree/pr/volpiano-neumes): Make a volpiano neume hold every note of its run

### Braille

- [`pr/braille-chord-symbol-duration`](https://github.com/float3/music21/tree/pr/braille-chord-symbol-duration): Use the chord's own duration in braille chordToBraille
- [`pr/braille-split-measure-padding-2`](https://github.com/float3/music21/tree/pr/braille-split-measure-padding-2): Pad split measures with zero-length rests in braille splitMeasure (open: [#2161](https://github.com/cuthbertLab/music21/pull/2161))
- [`pr/braille-fix-articulations-iteration`](https://github.com/float3/music21/tree/pr/braille-fix-articulations-iteration): Remove every doubled articulation in BrailleSegment.fixArticulations
- [`pr/braille-descending-chords-default`](https://github.com/float3/music21/tree/pr/braille-descending-chords-default): Spell braille chords downward by default and keep the clef's direction
- [`pr/braille-grand-segment-same-hand-keys-2`](https://github.com/float3/music21/tree/pr/braille-grand-segment-same-hand-keys-2): Yield every key of one hand in BrailleGrandSegment.yieldCombinedGroupingKeys (open: [#2170](https://github.com/cuthbertLab/music21/pull/2170))
- [`pr/braille-fix-articulation-tie-edges`](https://github.com/float3/music21/tree/pr/braille-fix-articulation-tie-edges): Keep a braille tie across a segment break in fixArticulations
