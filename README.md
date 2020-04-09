# How Does Do an Apertium
An attempt at a unified Apertium tutorial

# Table of Contents

For each subject in the table below, the first link is a general introduction and the second describes more technical details if you're curious or are running into more complex bugs.

| Subject | Summary |
| ------- | ------- |
| [Background: Why?](background_rbmt.md)<br>[Background: Bash](background_bash.md) | An overview of Rule-Based Machine Translation (RBMT), Apertium, and how to use the Bash command line |
| [Pipeline](pipeline.md)<br>[Pipeline (technical)](pipeline_tech.md) | How the different pieces of Apertium fit together |
| [Setup](setup.md)<br>[Setup (technical)](setup_tech.md) | How to get existing Apertium language data and set up new languages and pairs |
| [Morphological Transducers: General](transducer.md)<br>[Morphological Transducers (technical)](transducer_tech.md) | What transducers are and how they are used for morphological analysis and generation |
| [Morphological Transducers: Lttoolbox](transducer_lt.md)<br>[Morphological Transducers: Lttoolbox (technical)](transducer_lt_tech.md) | Dealing with transducers created with Lttoolbox |
| [Morphological Transducers: HFST](transducer_hfst.md)<br>[Morphological Transducers: HFST (technical)](transducer_hfst_tech.md) | Dealing with transducers created with HFST |
| [Morphological Disambiguation](disambiguation.md)<br>[Morphological Disambiguation (technical)](disambiguation_tech.md) | Processing ambiguous forms of words |
| [Multi-Word Expressions](separable.md)<br>[Multi-Word Expressions (technical)](separable_tech.md) | Using apertium-separable to deal with expressions that should be treated as single words |
| [Bilingual Dictionaries](biltrans.md)<br>[Bilingual Dictionaries (technical)](biltrans_tech.md) | |
| [Lexical Selection](lexsel.md)<br>[Lexical Selection (technical)](lexsel_tech.md) | Choosing the correct translations for words based on context |
| [Anaphora Resolution](anaphora.md)<br>[Anaphora Resolution (technical)](anaphora_tech.md) | Determining what things like pronouns refer to |
| [Structural Transfer: General](transfer.md) | Dealing with changes in word order and grammatical information |
| [Structural Transfer: Chunking](chunk.md)<br>[Structural Transfer: Chunking (technical)](chunk_tech.md) | Structural transfer using finite-state chunking |
| [Structural Transfer: Recursive](recursive.md)<br>[Structural Transfer: Recursive (technical)](recursive_tech.md) | Structural transfer using apertium-recursive |
| [Post-Generation](postgen.md)<br>[Post-Generation (technical)](postgen_tech.md) | Dealing with inter-word orthographic changes |
