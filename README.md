__W.I.P__

## Use cases

1. Provide a single query to get all samples in one project. 

   __Solution__: Get a list of sample accessions -> append new attribute "project" through curation -> Submit curation

2. Update ontology annotations with deprecated ontology terms to new ontology terms

    __Solution__: Get a list of sample acessions -> identify the attribute that contains the deprecated ontology term -> update the iri in that attribute -> submit curation

3. Update sample relationship

   __Solution*__: (Might related to sample relationship deprecation)
   
   Get a list of samples accessions --> identify the attribute that contains the deprecated ontology term --> submit curation
   
## Steps

1. Get accessions
   - Using common text search
   - Search with time range
   - search using accessions 
   - search with ontology term ID
   - search all samples containing attribute A
   - search all samples containing attribute A and value A
2. Identify the attribute (characteristics)
3. Generate updated data
4. Submit curation 
  - less than 100 sample (token valid for 1 hour only)
  - >100 sample (need to refresh token)
  
ideal command:

```
curate find
                -t "text"
                -id "accession"
                -attr "host age"
                -value "26 year" // must have -attr
                -r "find relationship" //not sure if this is possible
        update  
                -f "json file containing new characteristics"
                -d "json data. 
                -r "new relationships"// depended on "find -r". Not sure if possible
        push    -pwd  //only needed in buld subs. pwd in a json format file
```
   
