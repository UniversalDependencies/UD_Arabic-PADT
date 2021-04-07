# Summary

The Arabic-PADT UD treebank is based on the
[Prague Arabic Dependency Treebank](http://ufal.mff.cuni.cz/padt/) (PADT),
created at the Charles University in Prague.


# Introduction

http://universaldependencies.github.io/docs/ar/overview/introduction.html

The treebank consists of 7,664 sentences (282,384 tokens) and its domain is mainly newswire.
The annotation is licensed under the terms of
[CC BY-NC-SA 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
and its original (non-UD) version can be downloaded from
[http://hdl.handle.net/11858/00-097C-0000-0001-4872-3](http://hdl.handle.net/11858/00-097C-0000-0001-4872-3).

The morphological and syntactic annotation of the Arabic UD treebank is created through
conversion of PADT data. The conversion procedure has been designed by Dan Zeman.
The main coordinator of the original PADT project was Otakar Smrž.

### Source of annotations

This table summarizes the origins and checking of the various columns of the CoNLL-U data.

| Column | Status |
| ------ | ------ |
| ID | Sentence-level units in PADT often correspond to entire paragraphs and they were obtained automatically. Low-level tokenization (whitespace and punctuation) was done automatically and then hand-corrected. Splitting of fused tokens into syntactic words in Arabic is part of morphological analysis. [ElixirFM](http://elixir-fm.sf.net/) was used to provide context-independent options, then these results were disambiguated manually. |
| FORM | The unvocalized surface form is used. Fully vocalized counterpart can be found in the MISC column as Vform attribute. |
| LEMMA | Plausible analyses provided by ElixirFM, manual disambiguation. Lemmas are vocalized. Part of the selection of lemmas was also word sense disambiguation of the lexemes, providing English equivalents (see the Gloss attribute of the MISC column). |
| UPOSTAG | Converted automatically from XPOSTAG (via [Interset](http://ufal.mff.cuni.cz/interset)); human checking of patterns revealed by automatic consistency tests. |
| XPOSTAG | Manual selection from possibilities provided by ElixirFM. |
| FEATS | Converted automatically from XPOSTAG (via Interset); human checking of patterns revealed by automatic consistency tests. |
| HEAD | Original PADT annotation is manual. Automatic conversion to UD; human checking of patterns revealed by automatic consistency tests. |
| DEPREL | Original PDT annotation is manual. Automatic conversion to UD; human checking of patterns revealed by automatic consistency tests. |
| DEPS | &mdash; (currently unused) |
| MISC | Information about token spacing taken from PADT annotation. Additional word attributes provided by morphological analysis (i.e. ElixirFM rules + manual disambiguation): Vform (fully vocalized Arabic form), Translit (Latin transliteration of word form), LTranslit (Latin transliteration of lemma), Root (word root), Gloss (English translation of lemma). |


# Acknowledgments

We wish to thank all of the contributors to the original PADT annotation effort, including
Otakar Smrž, Jan Hajič, Petr Zemánek, Petr Pajas, Jan Šnaidauf, Emanuel Beška, Jakub Kráčmar,
and Kamila Hassanová.

Further corrections of additional data (not part of PADT release 1.0) were done by
Shadi Saleh and Zdeněk Žabokrtský.


## References

* Jan Hajič, Otakar Smrž, Petr Zemánek, Petr Pajas, Jan Šnaidauf, Emanuel Beška, Jakub Kráčmar,
  Kamila Hassanová. 2009.
  Prague Arabic Dependency Treebank 1.0, LINDAT/CLARIN digital library at
  Institute of Formal and Applied Linguistics, Charles University in Prague,
  [http://hdl.handle.net/11858/00-097C-0000-0001-4872-3](http://hdl.handle.net/11858/00-097C-0000-0001-4872-3).
* Otakar Smrž, Viktor Bielický, Iveta Kouřilová, Jakub Kráčmar, Jan Hajič, Petr Zemánek. 2008.
  Prague Arabic Dependency Treebank: A Word on the Million Words.
  In: Proceedings of the Workshop on Arabic and Local Languages (LREC 2008), pp. 16–23.
  Marrakech, Morocco.


# Changelog

* 2021-05-15 v2.8
  * Fixed order of multi-word lemmas in enhanced deprels.

* 2020-05-15 v2.6
  * Added enhanced relations with case information.
  * Added empty nodes to enhanced graphs (but orphans are just converted to dep).
  * Added enhanced relations around relative clauses.
  * Distinguishing SCONJ from CCONJ.

* 2019-05-15 v2.4
  * Fixed various bugs found by the new UD validator.

* 2018-11-15 v2.3
  * Fixed partial word forms of those multiword tokens where original morphological analysis
    was not disambiguated but existed.

* 2018-04-15 v2.2
  * Repository renamed from UD_Arabic to UD_Arabic-PADT.
  * Added enhanced representation of dependencies propagated across coordination.
    The distinction of shared and private dependents is derived deterministically from the original Prague annotation.
  * Prepositional objects are now obl:arg.
  * Fixed relative pronouns that were attached as 'cc' to their antecedents.
  * Multi-word prepositions annotated with the 'fixed' relation.

* 2017-03-01 v2.0
  * Converted to UD v2 guidelines.
  * Reconsidered PRON vs. DET.
  * Improved advmod vs. obl distinction.
  * Changed train-dev-test split to be compatible with UD_Arabic-NYUAD, which in turn follows Diab et al.
    (Mona Diab, Nizar Habash, Owen Rambow, Ryan Roth. 2013. LDC Arabic treebanks and associated corpora:
    Data divisions manual. arXiv preprint arXiv:1309.5652.)
    Some documents appear both in UD_Arabic and in UD_Arabic-NYUAD, and we want these to end up in the same section in both treebanks.

* 2016-05-15 v1.3
  * Unvocalized surface forms are now the main word forms in the FORM column. Fused tokens are shown. Vocalized forms available as MISC attributes.
  * Added lemmas, roots, transliteration and English glosses.
  * The _%_ symbols are now attached as `nmod` instead of `cc`.
  * Chains of auxiliaries have been removed as the negative copula لَيسَ / _laysa_ is now treated as copula and not as auxiliary verb.
  * Fixed adverbs that were attached as nmod; correct: advmod.
  * Fixed sentence ids.
  * Added the MISC attribute SpaceAfter=No.
  * Improved conversion of AuxY.

* 2015-11-15 v1.2
  * Modified version from HamleDT 3.0


=== Machine-readable metadata (DO NOT REMOVE!) ================================
Data available since: UD v1.2
License: CC BY-NC-SA 3.0
Includes text: yes
Genre: news
Lemmas: converted from manual
UPOS: converted from manual
XPOS: manual native
Features: converted from manual
Relations: converted from manual
Contributors: Zeman, Daniel; Žabokrtský, Zdeněk; Saleh, Shadi
Contributing: elsewhere
Contact: zeman@ufal.mff.cuni.cz
===============================================================================
