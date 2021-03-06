# rpa-school-dataset
[![DOI](https://zenodo.org/badge/459593715.svg)](https://zenodo.org/badge/latestdoi/459593715)

Polish schools dataset for Robotic Process Automation tasks. The paper describing the dataset is currently in review.

The data was sourced from the Polish registry of schools [(RSPO, *Rejestr Szkół i Placówek Oświatowych*)](https://rspo.gov.pl/). It is intended to be used in RPA and NER-related research. The dataset is entirely in the Polish language.

## Dataset
The dataset consists of three directories – `screenshots`, `hocr`, `metadata`. They contain files with corresponding names with different extensions that constitute a single example in the dataset.

- `screenshots` – screenshots of the RSPO website. Each screenshot contains exactly one school from the registry.
- `hocr` – HOCR files generated by Tesseract OCR software for each of the screenshots.
- `metadata` – JSON files in a pseudo-JSON-LD format. The format is described below.

There are three data series in this dataset:

- `School` – 92 screenshots of the unmodified RSPO website.
- `School_flip` – 75 screenshots where the field layout was flipped (rows to columns).
- `School_shuffle` – 84 screenshots where the field layout was shuffled randomly for each example.

### Metadata format

The following field types are used:

- `address`
  - `postalCode` – Polish postal code.
  - `streetAddress` – street name and building number. Can be just a number in some cases (e.g., villages).
  - `addressLocality` – town name.
- `name` – the official name of the school.
- `foundingDate` – when the school was founded. This field can vary in precision.
- `regon` – REGON (*Rejestr Gospodarki Narodowej*) identifier, assigned to juridical persons and other entities.
- `email` – contact email address of the school.
- `telephone` – phone number of the school.

Each field has the following attributes:

- `value` – the value of the field **as recognized by the OCR software**.
- `trueValue` – the true value of the field, **as obtained from the RSPO database**. This is usually the same as `value`, but the OCR method is not perfect and differences occur.
- `elemId` – an array of HOCR element identifiers that make up this piece of text. You can cross-reference these IDs with the provided HOCR files.

## Authors
The dataset was prepared by [Piotr Sowiński](https://orcid.org/0000-0002-2543-9461) and [Aleksander Denisiuk](https://orcid.org/0000-0002-7501-7048).

## License
This dataset is released under the [CC0 1.0 Universal license](https://creativecommons.org/publicdomain/zero/1.0/deed.en). This means (in short) that you are free to use it for whatever purpose, without any restrictions. We would, however, appreciate you citing the source of the data. You can use the following DOI: [![DOI](https://zenodo.org/badge/459593715.svg)](https://zenodo.org/badge/latestdoi/459593715)

The dataset contains screenshots of the [RSPO website](https://rspo.gov.pl/). We claim that they do not constitute copyrightable content, as they are composed simple rectangular shapes and text (contact information).
