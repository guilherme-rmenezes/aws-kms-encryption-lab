{\rtf1\ansi\ansicpg1252\cocoartf2868
\cocoatextscaling0\cocoaplatform0{\fonttbl\f0\fswiss\fcharset0 Helvetica;}
{\colortbl;\red255\green255\blue255;}
{\*\expandedcolortbl;;}
\paperw11900\paperh16840\margl1440\margr1440\vieww11520\viewh8400\viewkind0
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0

\f0\fs24 \cf0 # AWS KMS Encryption Lab\
\
This project demonstrates how to secure data at rest using AWS Key Management Service (KMS).\
\
The lab includes encryption for:\
\
- Amazon S3 objects\
- Amazon EC2 root volumes (EBS)\
- CloudTrail auditing\
- Key lifecycle impact on access\
\
\
\
## Initial Architecture\
\
The lab environment starts with an EC2 instance and an S3 bucket.\
\
![Start Architecture](architecture/start-arch.png)\
\
\
\
## Uploading an Encrypted Object to S3\
\
The image was uploaded using SSE-KMS encryption.\
\
![Encrypted Upload](flow/upload-encrypted-s3.png)\
\
\
\
## Public Access Attempt\
\
Even after making the object public, access is denied.\
\
![Access Denied](errors/access-denied1.png)\
\
\
\
## Access without Signature\
\
Requests without AWS Signature v4 fail.\
\
![Invalid Signature](errors/invalid-arguement.png)\
\
\
\
## Authenticated Access\
\
When accessed via AWS Console, the object is decrypted.\
\
![Signed Access](flow/open-signed.png)\
\
\
\
## CloudTrail Logging\
\
CloudTrail records the use of the KMS key.\
\
![CloudTrail Event](logs/gen-data-key-event.png)\
\
\
\
## Encrypting the EC2 Root Volume\
\
Process used to encrypt an existing root volume:\
\
![EBS Encryption Process](flow/vol-snap-vol.png)\
\
\
\
## Key Disabled Impact\
\
Disabling the KMS key prevents access to encrypted resources.\
\
![KMS Disabled Error](errors/create-grant-error.png)\
\
\
\
## Final Architecture\
\
After encryption:\
\
- S3 object encrypted\
- EC2 root volume encrypted\
- KMS manages keys\
- CloudTrail logs usage\
\
![Final Architecture](architecture/end-arch.png)\
\
\
\
## Sample Encryped Object\
\
![Clock Image](sample/clock.png)\
\
\
\
## Security Concepts Demonstrated\
\
- AWS KMS encryption\
- Encryption at rest\
- Envelope encryption\
- Key lifecycle impact\
- CloudTrail auditing\
- Secure access control\
\
\
\
## Skills Demonstrated\
\
- AWS KMS key management\
- S3 SSE-KMS encryption\
- EBS encryption migration\
- CloudTrail auditing\
- Cloud security best practices\
}