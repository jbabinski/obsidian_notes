Data sink - endpoint for ETL, e.g. data warehouse.

Options:
- [[Cloud Storage]]
- [[Cloud SQL]]
- [[Cloud Spanner]]
- [[Firestore]]
- [[Cloud BigTable]]

The method you use depends on how much transformation is needed:
- Extract and load **EL** - when the file is compatible with Google tool, i.e. avro, parquet.
- Extract, load, transform **ELT** - data isn't in the final format or you need to do other transformation. To be used when you don't need massive transformation effort.
- Extract, transform, load **ETL** - when you want to apply a number of transformations between the source and target Google product.




