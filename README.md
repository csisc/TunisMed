# TunisMed
A Project aiming to update the bibliographic metadata of *La Tunisie Médicale*, a peer-reviewed scholarly journal from Tunisia, in *Wikidata*, an open, collaborative and multilingual multidisciplinary knowledge graph.

* User Interface: https://w.wiki/9yX5
* Scholia Profile: https://scholia.toolforge.org/venue/Q3213360

# Description
The bibliographic metadata is retrieved from PubMed. Then, the metadata are manually processed using Excel and OpenRefine. Finally, they are uploaded to Wikidata using OpenRefine:
- **pubmed-LaTunisiem-set (1).txt**: The PubMed file including the bibliographic metadata of all the scholarly publications indexed in PubMed.
- **PubMed_file_to_Excel**: Converts the retrieved PubMed file into an Excel spreadsheet.
- **output.xlsx**: The Excel spreadsheet including all the metadata retrieved from PubMed.
- **output_s.xlsx**: A subset of the Excel spreadsheet including some of the columns.
- **output_s-excel-openrefine.xlsx**: A final edition of *output_s.xlsx* cleaned using Excel and OpenRefine and reconciled to Wikidata items.
- **wikidata-schema-openrefine.json**: The Wikibase schema for uploading the bibliographic metadata in *output_s-excel-openrefine.xlsx* to Wikidata.
- **output_authors.xlsx**: A subset of the Excel spreadsheet including author names.
- **output-authors-triples-finished.xlsx**: An Excel spreadsheet featuring author-publication links. Only authors ranked 36<sup>th</sup> or less have been considered.
- **wikibase-schema-authors.json**: The Wikibase schema for uploading the author information in *output-authors-triples-finished.xlsx* to Wikidata.
- **output_keywords_titles_abstracts.xlsx**: A subset of the Excel spreadsheet using titles, abstracts, and keywords.
- **generating-tables-for-keywords**: Generates two Excel spreadsheets for MeSH-publication and keyword-publication pairs.
- **mesh_keywords.xlsx**: The Excel spreadsheet for MeSH-publication pairs.
- **keywords.xlsx**: The Excel spreadsheet for keyword-publication pairs.
- **output-titles-abstracts.xlsx**: The Excel spreadsheet featuring the title and abstract of every single publication in English.
- **ui.sparql**: The source code of the user interface of the database.
- **mesh-keywords-xlsx.xlsx**: The Excel spreadsheet for MeSH-publication pairs after removing non-specific keywords and reconciliation to Wikidata.
- **mesh-schema.json**: The Wikibase schema for uploading MeSH Keywords to Wikidata.
- **keywords-xlsx.xlsx**: The Excel spreadsheet for keyword-publication pairs after removing non-specific keywords and reconciliation to Wikidata.
- **keywords-schema.json**: The Wikibase schema for uploading non-MeSH Keywords to Wikidata.
- **adding-ocr-to-pdf**: Adds an OCR layer to the PDF digitized edition of every volume of La Tunisie Médicale.
- **Retrieving-titles-from-ocr**: Retrieves the title of every single publication and the page where it exists from the OCR of the processed PDF.

# Data Model
| Property | Name                        | Notes                                                                                                   | Object                           |
|----------|-----------------------------|---------------------------------------------------------------------------------------------------------|----------------------------------|
| P31      | instance of                 |                                                                                                         | *scholarly article* (Q13442814)  |
| P1476    | title                       |                                                                                                         | monolingual text                 |
| P921     | main subject                | *has use* (P366) is used to define the field where the keyword has been defined in PubMed               | Wikidata item                    |
| P2093    | author name string          | *series ordinal* (P1545) is used to define the rank of the author                                       | string                           |
| P407     | language of work or name    |                                                                                                         | Wikidata item                    |
| P577     | publication date            |                                                                                                         | datetime                         |
| P1433    | published in                |                                                                                                         | *La Tunisie Médicale* (Q3213360) |
| P478     | volume                      |                                                                                                         | string                           |
| P304     | page(s)                     |                                                                                                         | string                           |
| P953     | full work available at URL  | *digitised by* (P8791) is used to define the institution that digitized the publication                 | string                           |
| P698     | PubMed ID                   |                                                                                                         | external identifier              |
| P356     | DOI                         |                                                                                                         | external identifier              |
