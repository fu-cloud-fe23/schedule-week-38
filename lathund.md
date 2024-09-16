# Lathund för att konfigurera din S3 bucket

## Steg 1

Gå till *Permissions* och leta upp *Block public access*. Den skall vara "off".

## Steg 2

Lite längre ner under *Permissions* hittar du *Bucket policy*. Klicka på *Edit* och lägg in följande policy (glöm inte att skriva in din buckets namn): 

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::<ditt-bucket-namn>/*"
        }
    ]
}
```

## Steg 3

1. Gå in på *Properties*-fliken istället och scrolla hela vägen ner till du kommer till *Static website hosting*.
2. Klicka på *Edit* och välj "Enable" under rubriken *Static website hosting*.
3. *Hosting type* skall vara "Statc website".
4. Under *Index document* skriver du "index.html".
5. Spara dina ändringar.
