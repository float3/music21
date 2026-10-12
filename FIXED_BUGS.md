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

## Fixed here, not yet upstream

### Streams

- [`pr/offset-filter-snapped-end`](https://github.com/float3/music21/tree/pr/offset-filter-snapped-end): Snap the end of a one-offset search as its start is snapped
- [`pr/augment-lazy-tuplets`](https://github.com/float3/music21/tree/pr/augment-lazy-tuplets): Keep tuplets set on a duration that has not worked out its own
- [`pr/beat-partial-measure-meter`](https://github.com/float3/music21/tree/pr/beat-partial-measure-meter): Count a split measure's second half in the meter its first half opens with
- [`pr/split-measure-time-signature`](https://github.com/float3/music21/tree/pr/split-measure-time-signature): Give a split measure's second half the clef, key and meter in force where it is split
- [`pr/split-keeps-right-barline`](https://github.com/float3/music21/tree/pr/split-keeps-right-barline): Keep a split measure's right barline at the end of its second half
- [`pr/greatest-divisor-grace-notes`](https://github.com/float3/music21/tree/pr/greatest-divisor-grace-notes): Slice by the greatest divisor past grace notes and empty measures
- [`pr/slice-at-offsets-voices`](https://github.com/float3/music21/tree/pr/slice-at-offsets-voices): Keep the pieces of a note cut in a voice in that voice
- [`pr/find-consecutive-unisons`](https://github.com/float3/music21/tree/pr/find-consecutive-unisons): Fix findConsecutiveNotes(skipUnisons=True) on repeated notes and chords
- [`pr/melodic-intervals-offsets`](https://github.com/float3/music21/tree/pr/melodic-intervals-offsets): Place melodicIntervals at offsets in the stream analysed
- [`pr/partstaff-measure-gap`](https://github.com/float3/music21/tree/pr/partstaff-measure-gap): Join PartStaffs after a measure missing from the first staff

### Analysis and features

- [`pr/windowed-adjacent-average`](https://github.com/float3/music21/tree/pr/windowed-adjacent-average): Allow adjacentAverage windowed analysis with windows above size one
- [`pr/floating-key-interpretation-copy`](https://github.com/float3/music21/tree/pr/floating-key-interpretation-copy): Smooth floating key analysis with each neighbour's own interpretations
- [`pr/empty-tree-verticalities`](https://github.com/float3/music21/tree/pr/empty-tree-verticalities): Yield no verticalities from an empty TimespanTree
- [`pr/chord-reducer-hashable-timespans`](https://github.com/float3/music21/tree/pr/chord-reducer-hashable-timespans): Make ElementTimespan hashable
- [`pr/verticality-part-id-chord-notes`](https://github.com/float3/music21/tree/pr/verticality-part-id-chord-notes): Give chord notes part id groups in Verticality.makeElement
- [`pr/most-common-rhythms-chord`](https://github.com/float3/music21/tree/pr/most-common-rhythms-chord): Allow chords and unpitched notes in mostCommonMeasureRhythms
- [`pr/chord-bass-motion-no-chord`](https://github.com/float3/music21/tree/pr/chord-bass-motion-no-chord): Skip NoChord in ChordBassMotionFeature
- [`pr/chord-bass-motion-direction`](https://github.com/float3/music21/tree/pr/chord-bass-motion-direction): Count ChordBassMotionFeature motion upward
- [`pr/quality-feature-modal-key`](https://github.com/float3/music21/tree/pr/quality-feature-modal-key): Analyze modal keys in QualityFeature
- [`pr/extractors-by-id-all`](https://github.com/float3/music21/tree/pr/extractors-by-id-all): Include native extractors in extractorsById(library='all')
- [`pr/output-tab-orange-include-id`](https://github.com/float3/music21/tree/pr/output-tab-orange-include-id): Honor includeId and includeClassLabel in Orange and ARFF rows
- [`pr/features-as-list-rows`](https://github.com/float3/music21/tree/pr/features-as-list-rows): Return one row per instance from getFeaturesAsList
- [`pr/part-reduction-span-start`](https://github.com/float3/music21/tree/pr/part-reduction-span-start): Keep the stretch before a span's first dynamic in PartReduction
- [`pr/part-reduction-same-ids`](https://github.com/float3/music21/tree/pr/part-reduction-same-ids): Keep each part's spans apart in PartReduction when ids repeat
- [`pr/part-reduction-leave-dynamics`](https://github.com/float3/music21/tree/pr/part-reduction-leave-dynamics): Leave the score's dynamics unchanged in PartReduction
- [`pr/part-reduction-dynamic-on-barline`](https://github.com/float3/music21/tree/pr/part-reduction-dynamic-on-barline): Start each PartReduction span at the last dynamic before it
- [`pr/part-reduction-average-weight`](https://github.com/float3/music21/tree/pr/part-reduction-average-weight): Average dynamics in PartReduction weights
- [`pr/part-reduction-whole-word-groups`](https://github.com/float3/music21/tree/pr/part-reduction-whole-word-groups): Match PartReduction part groups on whole words of the part id
- [`pr/reductive-note-chord-highest`](https://github.com/float3/music21/tree/pr/reductive-note-chord-highest): Take a chord's highest note when a ReductiveNote names no pitch
- [`pr/score-reduction-lone-part`](https://github.com/float3/music21/tree/pr/score-reduction-lone-part): Wrap a lone Part in a Score in ScoreReduction.score
- [`pr/dolan-part-groups`](https://github.com/float3/music21/tree/pr/dolan-part-groups): Set Dolan's default part groups when a stream is given

### Audio

- [`pr/autocorrelation-int16-overflow`](https://github.com/float3/music21/tree/pr/autocorrelation-int16-overflow): Find frequencies from sixteen-bit samples without scipy

### Scales and figured bass

- [`pr/octave-repeating-full-octave`](https://github.com/float3/music21/tree/pr/octave-repeating-full-octave): Close an octave-repeating scale without a zero-width step
- [`pr/harmonic-minor-no-altered-degrees`](https://github.com/float3/music21/tree/pr/harmonic-minor-no-altered-degrees): Build harmonic minor from its own intervals
- [`pr/next-pitch-wide-cycles`](https://github.com/float3/music21/tree/pr/next-pitch-wide-cycles): Find nextPitch neighbors on cycles wider than an octave
- [`pr/relative-node-id-deterministic`](https://github.com/float3/music21/tree/pr/relative-node-id-deterministic): Choose among nodes sharing a pitch without randomness
- [`pr/sieve-complement-empty`](https://github.com/float3/music21/tree/pr/sieve-complement-empty): Take the complement of an empty residual class in sieve
- [`pr/fb-realizer-own-pitches`](https://github.com/float3/music21/tree/pr/fb-realizer-own-pitches): Give figured-bass realizations their own pitches
- [`pr/fb-tuplet-offsets`](https://github.com/float3/music21/tree/pr/fb-tuplet-offsets): Realize figured-bass lines holding tuplets

### Metadata

- [`pr/metadata-search-uncompilable`](https://github.com/float3/music21/tree/pr/metadata-search-uncompilable): Search metadata for a query that will not compile as a pattern

### Formats

- [`pr/abc-rebar-overflow`](https://github.com/float3/music21/tree/pr/abc-rebar-overflow): Keep the overflow of an ABC measure when no time signature fits it
- [`pr/capella-barline-tuplet`](https://github.com/float3/music21/tree/pr/capella-barline-tuplet): Read Capella single barlines and prolonged tuplets
- [`pr/humdrum-nested-split`](https://github.com/float3/music21/tree/pr/humdrum-nested-split): Insert nested Humdrum sub-spines bottom-up
- [`pr/midi-deduplicate-instruments`](https://github.com/float3/music21/tree/pr/midi-deduplicate-instruments): Deduplicate instruments offset by offset
- [`pr/musedata-stage1-part-name`](https://github.com/float3/music21/tree/pr/musedata-stage1-part-name): Leave a stage-1 MuseData part without a name
- [`pr/musicxml-arpeggio-single-note`](https://github.com/float3/music21/tree/pr/musicxml-arpeggio-single-note): Write an arpeggio mark on a single note to MusicXML
- [`pr/chord-to-xml-sorted`](https://github.com/float3/music21/tree/pr/chord-to-xml-sorted): Sort chords in place before MusicXML export
- [`pr/trill-accidental-display`](https://github.com/float3/music21/tree/pr/trill-accidental-display): Decide a trill's undecided ornamental accidental
- [`pr/noteworthy-clef-names`](https://github.com/float3/music21/tree/pr/noteworthy-clef-names): Separate Tenor and Percussion in noteworthy ClefNames
- [`pr/nwctxt-chord-groups`](https://github.com/float3/music21/tree/pr/nwctxt-chord-groups): Read NWC Dur2/Pos2 chord notes and rest chords at the same offset
- [`pr/nwc-binary-chords`](https://github.com/float3/music21/tree/pr/nwc-binary-chords): Read chord and rest-chord notes in binary NWC files
- [`pr/nwc-chord-dump`](https://github.com/float3/music21/tree/pr/nwc-chord-dump): Dump binary NWC chords as Dur2/Pos2 and rest chords as RestChord
- [`pr/romantext-high-numerals`](https://github.com/float3/music21/tree/pr/romantext-high-numerals): Reject roman numerals past VII
- [`pr/tinynotation-close-states`](https://github.com/float3/music21/tree/pr/tinynotation-close-states): Close TinyNotation brackets past ties and time signatures
- [`pr/volpiano-current-measure`](https://github.com/float3/music21/tree/pr/volpiano-current-measure): Put volpiano breaks and neumes in the measure being read
- [`pr/volpiano-end-breaks-layout`](https://github.com/float3/music21/tree/pr/volpiano-end-breaks-layout): Make volpiano breaks at the end of the text follow breaksToLayout
- [`pr/volpiano-neumes`](https://github.com/float3/music21/tree/pr/volpiano-neumes): Make a volpiano neume hold every note of its run
