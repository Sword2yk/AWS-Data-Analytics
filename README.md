# AWS-Data-Analytics

How to pass AWS Data Analytics Specialty (AWS DAS-C01): tips and personal experience

I successfully passed the AWS DAS yesterday, got the result today (854), and here are the tips for people who are planning to take the test.

# General:

* **Stephane Maarek & Frank Kane's** ([https://www.udemy.com/course/aws-data-analytics/](https://www.udemy.com/course/aws-data-analytics/)) course on Udemy is good, but it won't cover everything you need to know. Make sure you go through FAQ's and documentation for the areas you are not confident in. (tip: use a new udemy account to get a discount)
* Purchase an additional preparation test set from Maarek ([https://www.udemy.com/course/practice-exams-aws-certified-data-analytics-specialty/](https://www.udemy.com/course/practice-exams-aws-certified-data-analytics-specialty/)), it is worth it. It's quite close to the exam in terms of wording and question length.
* If you don't have any EMR experience and are worried about that - you shouldn't be. There are not that many *DETAILED* questions on EMR. You need to know which service does what (*Hive, HBase, Spark, Ivy, Mahout, Ganglia, Ranger, Pig, Presto*, etc.). You need to know how AWS services interact with EMR (Can you write from KDS to ERM? From Firehose? Can you use DMS to ingest data to EMR? Data Pipeline? How do you transfer data from EMR to Redshift? Can you run a Spark job in ERM? Do you have to restart/recreate a cluster to add a job? How do you add a job?)
* **Wizzlab** ([https://www.whizlabs.com/aws-certified-data-analytics-specialty/](https://www.whizlabs.com/aws-certified-data-analytics-specialty/)) practice tests are over complicated and can be used only to understand the areas in which you're not confident. If you get low scores, that's fine, just make sure to refresh related services/concepts. (I did 70%/40%/70%). You can also try **TuturialsDojo** practice tests ([https://portal.tutorialsdojo.com/courses/aws-certified-data-analytics-specialty-practice-exams/](https://portal.tutorialsdojo.com/courses/aws-certified-data-analytics-specialty-practice-exams/)) and **CloudAcademy** ([https://cloudacademy.com/learning-paths/aws-certified-data-analytics-specialty-das-c01-certification-preparation-for-aws-1804/](https://cloudacademy.com/learning-paths/aws-certified-data-analytics-specialty-das-c01-certification-preparation-for-aws-1804/) course and [https://cloudacademy.com/exam/landing/36790/](https://cloudacademy.com/exam/landing/36790/) test)
* Time to prepare: 2-6 months depending on the pace. It took me around 3 months, but I was taking breaks every now and then
* Solution Architect Associate/Developer Associate helps a lot. I would recommend taking SAA prior to DAS.

# How to Prepare

(I would've done it the way I describe below if I knew what I know now):

1. Take the course taking the notes (I use GitMind)
2. Read as many FAQs/Whitepapers/Docs as you can before losing motivation
3. When you feel like you're losing motivation (my biggest issue) - start taking exams (Maarek's, Wizzlabs, DoJo). While taking the exams, don't rush. After each test revisit the documentation and notes and add new knowledge that you obtained taking the tests. to the notes. This also helps you remember stuff.
4. Go through the course/notes again and check the areas that you are not confident about.
5. If you have enough time/patience/energy - go through the tests again
6. Pay more attention to security/high availability
7. Cross-account and cross-region for different services!
8. Be consistent. Keep yourself motivated. Do not take long breaks as it'll be difficult to resume.

&#x200B;

# Additional hints for the exam (questions/topics that I had in my exam):

* Spend more time understanding the security (especially **LakeFormation** \- how to grant & restrict access, when to use, what services are used under the hood, etc.). Know how to secure your glue catalog. Ideally, know what encryption can be used by different services (e.g. Can you use KMS customer managed key for Quicksight?). If you think you know it well enough - you don't. Go through the notes again.
* Learn formats: *ORC, Parquet, Avro*, and others. Which are splittable? Which are columnar? Which of them can be used in ERM? In Redshift Spectrum? In Quicksight? In S3 Select & Glacier Select? Can they be compressed for those services?
* Know which services are inside and outside your **VPC**. Some of them can be inside and outside depending on configuration. How do you access them from on-premise infrastructure? (There was a question about accessing Kibana from on-prem using direct connect and avoiding any public routes)
* Learn how to replicate data for **High Availability** (S3, Redshift, Opensearch, EMR)
* Know how to encrypt an unencrypted Redshift cluster (KMS vs. HSM)
* Know how to reference s3 files from Kinesis Data Analytics
* You can lower the JVM memory pressure by reducing the number of shards or upgrading to a larger cluster (**Opensearch**)
* How often you can invoke a glue job/crawler?
* Which type of node do you need to add to an EMR cluster when you get an error that says that there are no available nodes to write the data (core/task/master)
* Understand the difference between **instance groups** and **instance fleets** for EMR
* **S3**: storage tiers, lifecycle policies, Glacier, S3 Object Lock (WORM, compliance vs governance mode, Vault Lock)
* **Opensearch** dashboards, **Kibana**
* **Glue** job vs **Glue** workflow (and scheduling)
* Can DMS read from DynamoDB? Can DMS write to DynamoDB?
* Quicksight doesn't have access to a newly created bucket: how to fix?
* MSK metrics for monitoring (DEFAULT, PER\_TOPIC\_PER\_BROKER, PER\_TOPIC\_PER\_PARTITION) ([https://docs.aws.amazon.com/msk/latest/developerguide/metrics-details.html](https://docs.aws.amazon.com/msk/latest/developerguide/metrics-details.html))
* **Kinesis** ins and outs (mostly every questions has Kinesis as an option) (KDS, KDF + lambda, KDA + reference data)

&#x200B;

# Other reddit users on the exam:

I won't post many links to FAQs/whitepapers/videos because you can crawl the topics below and most probably you'll find everything you need:

[https://www.reddit.com/r/AWSCertifications/comments/15e17fo/passed\_dasc01\_data\_analytics\_specialty/](https://www.reddit.com/r/AWSCertifications/comments/15e17fo/passed_dasc01_data_analytics_specialty/)

[https://www.reddit.com/r/AWSCertifications/comments/i96zhv/passed\_aws\_certified\_data\_analytics\_specialty/](https://www.reddit.com/r/AWSCertifications/comments/i96zhv/passed_aws_certified_data_analytics_specialty/)

[https://www.reddit.com/r/AWSCertifications/comments/14ql4ve/passed\_aws\_data\_analytics\_specialty/](https://www.reddit.com/r/AWSCertifications/comments/14ql4ve/passed_aws_data_analytics_specialty/)

[https://www.reddit.com/r/AWSCertifications/comments/hsag0q/just\_passed\_the\_aws\_data\_analytics\_specialty\_cert/](https://www.reddit.com/r/AWSCertifications/comments/hsag0q/just_passed_the_aws_data_analytics_specialty_cert/)

[https://www.reddit.com/r/AWSCertifications/comments/hmw1sm/passed\_the\_data\_analytics\_specialty\_dasc01\_exam/](https://www.reddit.com/r/AWSCertifications/comments/hmw1sm/passed_the_data_analytics_specialty_dasc01_exam/)

[https://www.reddit.com/r/AWSCertifications/comments/158cclv/passed\_aws\_dasco1\_my\_first\_aws\_certification/](https://www.reddit.com/r/AWSCertifications/comments/158cclv/passed_aws_dasco1_my_first_aws_certification/)

[https://www.reddit.com/r/AWSCertifications/comments/l2yadl/my\_experience\_clearing\_the\_aws\_certified\_data/](https://www.reddit.com/r/AWSCertifications/comments/l2yadl/my_experience_clearing_the_aws_certified_data/)

[https://www.reddit.com/r/AWSCertifications/comments/145x6om/just\_learned\_i\_passed\_data\_analytics\_specialty/](https://www.reddit.com/r/AWSCertifications/comments/145x6om/just_learned_i_passed_data_analytics_specialty/)

[https://www.reddit.com/r/AWSCertifications/comments/14jqx9t/passed\_aws\_data\_analytics\_specialty/](https://www.reddit.com/r/AWSCertifications/comments/14jqx9t/passed_aws_data_analytics_specialty/)

&#x200B;

# Other sources:

[https://sidk17.medium.com/story-about-aws-data-analytics-certification-164b49e484f6](https://sidk17.medium.com/story-about-aws-data-analytics-certification-164b49e484f6)

[http://aws-reinvent-audio.s3-website.us-east-2.amazonaws.com/2018/2018.html](http://aws-reinvent-audio.s3-website.us-east-2.amazonaws.com/2018/2018.html)

[http://aws-reinvent-audio.s3-website.us-east-2.amazonaws.com/2019/2019.html](http://aws-reinvent-audio.s3-website.us-east-2.amazonaws.com/2019/2019.html)

[http://aws-reinvent-audio.s3-website.us-east-2.amazonaws.com/2020/2020.html](http://aws-reinvent-audio.s3-website.us-east-2.amazonaws.com/2020/2020.html)

[https://www.youtube.com/playlist?list=PL2yQDdvlhXf\_b\_a3X0Bd58WbEZGDau-lW](https://www.youtube.com/playlist?list=PL2yQDdvlhXf_b_a3X0Bd58WbEZGDau-lW) (2021)

&#x200B;

There are also a lot of links in Stephane Maarek's course (whitepapers & FAQ) and a lot of links to documentation in the mock exams (both in Wizzlab's and Maarek's)

&#x200B;

Good luck!
