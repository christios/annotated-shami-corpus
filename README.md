# Annotated Shami Corpus

This repository will contain the data which was annotated in the scope of my master's thesis which revolves around the standardization of orthography for Arabic dialects. It consists of a Lebanese Arabic corpus annotated for numerous morphological features and for orthography standardization. This [link](https://drive.google.com/file/d/1VA4PZ1UKKQmpJXi0JYkh8miuOsNMDk-U/view?usp=sharing) takes you to the report of the thesis where the annotation process and corpus statistics are described in detail in Chapter 3 (Lebanese Arabic Corpus Annotation).

## Disclaimer
This repository has yet to be polished and is still in the same state in which it was left at submission time. It was not in any way made to be user-friendly, and was pushed for the time being for purely administrative reasons. It will soon be overhauled and released in a form which is more readily usable.

## Data
This corpus is based on and annotates sentences from the [Shami Corpus](https://github.com/GU-CLASP/shami-corpus).
### Corpus Statistics
For the corpus statistics, please refer to Section 3.4.7 of the [thesis report](https://drive.google.com/file/d/1VA4PZ1UKKQmpJXi0JYkh8miuOsNMDk-U/view?usp=sharing).

### Corpus Contents
The data comes in the form of a JSON file which is a list of *sentence annotations*. Each *sentence annotation* is a JSON object which contains the annotations. Annotation objects are made up of the following:

Key | Value | Data Type
--- | --- | ---
`original` |  Contains the sentence as found in the original Shami Corpus. | `str`
`delimiters` | Internal variable which saves segmentation delimitations. | `list(int)`
`fixed` | Contains the manually preprocessed sentence in case the annotator uses the *Fix Sentence* option. Otherwise, it is left empty. | `str`
`raw` | List containing the source side of the source-target pairs. | `list(str)`
`coda` | List containing the target side of the source-target pairs (CODA* standardized). | `list(str)`
`taxonomy` | List containing the Spontaneous Orthography tags for each source-target pair. A source-target pair either has soruce and target equal, in which case the value is `"equal"`, or not, in which case one or more tags can be assigned to that pair. | `list(list(str) \| str)`
`segments` | This is actually a list of *tokens* and not *segments*. Each token is made up of one or more segments. One segment is a dictionary with the different features (described in the thesis report) as key/value pairs. | `list(list(dict(str, str)))`
