# ce8_assignment_2_15
Assignment 2.15

Answer the following:

1. What is needed to authorize your EC2 to retrieve secrets from the AWS Secret Manager?
   
Answer:

An IAM policy to access Secrets Manager (the policy JSON is as shown below). 

An IAM role and with the above created IAM policy attached to it.

Modify EC2 IAM role to include the role created in the step above. 


2. Derive the IAM policy (i.e. JSON)?

Answer:
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": [
                "secretsmanager:GetRandomPassword",
                "secretsmanager:ListSecrets",
                "secretsmanager:BatchGetSecretValue"
            ],
            "Resource": "*"
        },
        {
            "Sid": "VisualEditor1",
            "Effect": "Allow",
            "Action": "secretsmanager:*",
            "Resource": "arn:aws:secretsmanager:ap-southeast-1:255945442255:secret:prod/yl-cart-service/credentials-O7kbbY"
        }
    ]
}


3. Using the secret name prod/cart-service/credentials, derive a sensible ARN as the specific resource for access.

Answer:

arn:aws:secretsmanager:ap-southeast-1:255945442255:secret:prod/yl-cart-service/credentials-O7kbbY

