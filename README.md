# TunisMed
A Project aiming to update the bibliographic metadata of La Tunisie Médicale, a peer-reviewed scholarly journal from Tunisia, in Wikidata, an open, collaborative and multilingual multidisciplinary knowledge graph.

User Interface: https://w.wiki/9yW8

# Description
The bibliographic metadata is retrieved from PubMed. Then, the metadata are manually processed using Excel and OpenRefine. Finally, they are uploaded to Wikidata using OpenRefine:
- **pubmed-LaTunisiem-set (1).txt**: The PubMed file including the bibliographic metadata of all the scholarly publications indexed in PubMed.
- **PubMed_file_to_Excel**: Converts the retrieved PubMed file into an Excel spreadsheet.
- **output.xlsx**: The Excel spreadsheet including all the metadata retrieved from PubMed.
- **output_s.xlsx**: A subset of the Excel spreadsheet including some of the columns.
- **output_s-excel-openrefine.xlsx**: A final edition of *output_s.xlsx* cleaned using Excel and OpenRefine and reconciled to Wikidata items.
- **wikidata-schema-openrefine.json**: The Wikibase schema for uploading the bibliographic metadata in *output_s-excel-openrefine.xlsx* to Wikidata.
