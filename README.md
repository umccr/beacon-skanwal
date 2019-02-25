# beacon-skanwal
A federated ecosystem that allows sharing of genomic and clinical data


## Notes

The serverless beacon is up and running at [beacon](https://avt0y2mcq9.execute-api.ap-southeast-2.amazonaws.com/prod) (courtesy Florian).

### Data

Curently, it is pointing to one of the AGHA [gVCFs](s3://agha-gdr-store-dev/mitochondrial_disease/17W001163.dedup.realigned.recalibrated.hc.gvcf.gz) 

**Load data into beacon**

```
curl --header "Content-Type: application/json" \
  --request POST \
  --data '{"id":"t1","name":"test1","assemblyId":"GRCh37","vcfLocations": ["s3://umccr-primary-data-dev/bcbio_test_project_new/final/2018-12-05_2018-11-30T1125_Avner_WGS-merged/2016_249_18_WH_P017_1-ensemble-annotated.vcf.gz"]}' \
  https://avt0y2mcq9.execute-api.ap-southeast-2.amazonaws.com/prod/submit
```

### Example query

```
curl "https://avt0y2mcq9.execute-api.ap-southeast-2.amazonaws.com/prod/query?assemblyId=hg19;referenceName=1;referenceBases=C;alternateBases=T;start=10491;end=10491;includeDatasetResponses=HIT"
```

### Pointers

- Peformance comparison between serverless abd traditional beacons
- Try loading more data into the serverless beacon
- Create some (interesting and meaningful) queries

 


  

