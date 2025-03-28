![Version](https://img.shields.io/github/v/release/DCMLab/schulhoff_suite_dansante_en_jazz?display_name=tag)
[![DOI](https://zenodo.org/badge/517777050.svg)](https://doi.org/10.5281/zenodo.14997098)
![GitHub repo size](https://img.shields.io/github/repo-size/DCMLab/schulhoff_suite_dansante_en_jazz)
![License](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-9cf)


This is a README file for a data repository originating from the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora)
and serves as welcome page for both 

* the GitHub repo [https://github.com/DCMLab/schulhoff_suite_dansante_en_jazz](https://github.com/DCMLab/schulhoff_suite_dansante_en_jazz) and the corresponding
* documentation page [https://dcmlab.github.io/schulhoff_suite_dansante_en_jazz](https://dcmlab.github.io/schulhoff_suite_dansante_en_jazz)

For information on how to obtain and use the dataset, please refer to [this documentation page](https://dcmlab.github.io/schulhoff_suite_dansante_en_jazz/introduction).

# Erwin Schulhoff – Suite dansante en jazz (A corpus of annotated scores)

Austro-Czech composer Erwin Schulhoff had visions of a musical revolution. Inspired both by the absurdist aesthetic
theories of Dadaism and by the utopian social order promised by Communism, Schulhoff drew on dance forms and the
language of American jazz, promising a "complete escape from imperialistic tonality and rhythm." Schulhoff's work was
heavily censored by the Nazi regime and is rarely performed even today. In these annotations, it is notable how
Schulhoff uses an equalizing perpetual dissonance, frequently in the form of a long succession of dissonated secondary
dominants to tonics that never appear, to escape the hierarchic obligation of tonal harmony to resolve to the tonic
triad. This technique is an alternate approach to "emancipating the dissonance," to use Schoenberg's phrase, which is
nonetheless completely compatible with familiar sonorities.

## Getting the data

* download repository as a [ZIP file](https://github.com/DCMLab/schulhoff_suite_dansante_en_jazz/archive/main.zip)
* download a [Frictionless Datapackage](https://specs.frictionlessdata.io/data-package/) that includes concatenations
  of the TSV files in the four folders (`measures`, `notes`, `chords`, and `harmonies`) and a JSON descriptor:
  * [schulhoff_suite_dansante_en_jazz.zip](https://github.com/DCMLab/schulhoff_suite_dansante_en_jazz/releases/latest/download/schulhoff_suite_dansante_en_jazz.zip)
  * [schulhoff_suite_dansante_en_jazz.datapackage.json](https://github.com/DCMLab/schulhoff_suite_dansante_en_jazz/releases/latest/download/schulhoff_suite_dansante_en_jazz.datapackage.json)
* clone the repo: `git clone https://github.com/DCMLab/schulhoff_suite_dansante_en_jazz.git` 


## Data Formats

Each piece in this corpus is represented by five files with identical name prefixes, each in its own folder. 
For example, the first piece, *Stomp*, has the following files:

* `MS3/suite_dansante_en_jazz_1_stomp.mscx`: Uncompressed MuseScore 3.6.2 file including the music and annotation labels.
* `notes/suite_dansante_en_jazz_1_stomp.notes.tsv`: A table of all note heads contained in the score and their relevant features (not each of them represents an onset, some are tied together)
* `measures/suite_dansante_en_jazz_1_stomp.measures.tsv`: A table with relevant information about the measures in the score.
* `chords/suite_dansante_en_jazz_1_stomp.chords.tsv`: A table containing layer-wise unique onset positions with the musical markup (such as dynamics, articulation, lyrics, figured bass, etc.).
* `harmonies/suite_dansante_en_jazz_1_stomp.harmonies.tsv`: A table of the included harmony labels (including cadences and phrases) with their positions in the score.

Each TSV file comes with its own JSON descriptor that describes the meanings and datatypes of the columns ("fields") it contains,
follows the [Frictionless specification](https://specs.frictionlessdata.io/tabular-data-resource/),
and can be used to validate and correctly load the described file. 

### Opening Scores

After navigating to your local copy, you can open the scores in the folder `MS3` with the free and open source score
editor [MuseScore](https://musescore.org). Please note that the scores have been edited, annotated and tested with
[MuseScore 3.6.2](https://github.com/musescore/MuseScore/releases/tag/v3.6.2). 
MuseScore 4 has since been released which renders them correctly but cannot store them back in the same format.

### Opening TSV files in a spreadsheet

Tab-separated value (TSV) files are like Comma-separated value (CSV) files and can be opened with most modern text
editors. However, for correctly displaying the columns, you might want to use a spreadsheet or an addon for your
favourite text editor. When you use a spreadsheet such as Excel, it might annoy you by interpreting fractions as
dates. This can be circumvented by using `Data --> From Text/CSV` or the free alternative
[LibreOffice Calc](https://www.libreoffice.org/download/download/). Other than that, TSV data can be loaded with
every modern programming language.

### Loading TSV files in Python

Since the TSV files contain null values, lists, fractions, and numbers that are to be treated as strings, you may want
to use this code to load any TSV files related to this repository (provided you're doing it in Python). After a quick
`pip install -U ms3` (requires Python 3.10 or later) you'll be able to load any TSV like this:

```python
import ms3

labels = ms3.load_tsv("harmonies/suite_dansante_en_jazz_1_stomp.harmonies.tsv")
notes = ms3.load_tsv("notes/suite_dansante_en_jazz_1_stomp.notes.tsv")
```


## Version history

See the [GitHub releases](https://github.com/DCMLab/schulhoff_suite_dansante_en_jazz/releases).

## Questions, Suggestions, Corrections, Bug Reports

Please [create an issue](https://github.com/DCMLab/schulhoff_suite_dansante_en_jazz/issues) and/or feel free to fork and submit pull requests.

## Cite as

> Johannes Hentschel, Yannis Rammos, Markus Neuwirth, & Martin Rohrmeier. (2025). Erwin Schulhoff – Suite dansante en jazz (A corpus of annotated scores) [Data set]. Zenodo. https://doi.org/10.5281/zenodo.14997098

## License

Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)).

![cc-by-nc-sa-image](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)

## Overview
|            file_name            |measures|labels|standard|annotators |reviewers|
|---------------------------------|-------:|-----:|--------|-----------|---------|
|suite_dansante_en_jazz_1_stomp   |      46|    97|2.3.0   |Amelia Brey|DK       |
|suite_dansante_en_jazz_2_strait  |      39|    87|2.3.0   |Amelia Brey|DK       |
|suite_dansante_en_jazz_3_waltz   |      70|    92|2.3.0   |Amelia Brey|DK       |
|suite_dansante_en_jazz_4_tango   |      40|    63|2.3.0   |Amelia Brey|DK       |
|suite_dansante_en_jazz_5_slow    |      41|    96|2.3.0   |Amelia Brey|DK       |
|suite_dansante_en_jazz_6_fox-trot|      50|    53|2.3.0   |Amelia Brey|DK       |


*Overview table automatically updated using [ms3](https://ms3.readthedocs.io/).*
