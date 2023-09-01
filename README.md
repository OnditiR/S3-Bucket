# S3-Bucket
#Creating S3 Bucket
    aws s3api create-bucket --bucket my-example-bucket --region us-east-1
#Assigning Plocies to the Bucket
  #Bucket editing policy(Delete)- This policies prevents users from deleting the bucket
{
	"Version": "2012-10-17",
	"Id": "MyBucketPolicy",
	"Statement": [
		{
			"Sid": "BucketPutDelete",
			"Effect": "Deny",
			"Principal": "*",
			"Action": "s3:DeleteObject",
			"Resource": [
				"arn:aws:s3:::<bucket-name>/index.html",
				"arn:aws:s3:::<bucket-name>/script.js",
				"arn:aws:s3:::<bucket-name>/style.css"
        ]
		}
	]
}


