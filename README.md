## Mapping drug interactions – collagen tissue healing
## Research question - Which existing drugs interact with proteins involved in collagen fibril organization

All of the data filtering was done through the SPARQL query
## The query: 
- picks three biological processes by their Gene Ontology IDs:
  - GO:0030199 – collagen fibril organization
  - GO:0030198 – extracellular matrix organization
  - GO:0042060 – wound healing
- finds the proteins that take part in those processes (`P682`, biological process)
- finds the drugs that interact with those proteins (`P129`, physically interacts with). It checks both directions with a `UNION`, because Wikidata can record the link either way.
- keeps only compounds that have a **DrugBank ID** (`P715`), so the results are real drugs
- uses `SELECT DISTINCT` to remove duplicate rows

## Visualisation
results are shown in an interactive force-directed network graph built with D3.js in the Code.html file

