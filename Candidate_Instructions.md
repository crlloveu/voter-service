# Candidate AWS IAM User Information

## Decrypt Credentials File

ThoughtWorks has created an [AWS Identity and Access Management (IAM)](https://aws.amazon.com/iam/) User account for you. We have supplied your User account information to you in an encrypted AWS `credentials.csv` file. For example:

```text
User name,Password,Access key ID,Secret access key,Console login link
USER_C982F9C1D628,n3mw$xKa5![_,IKAFKSJ2XADWLCH63IV3,w4oGvn2EA9L3Lr37iyOYAQXByHeJ6l2PPH8Xkvp9,https://521292340873.signin.aws.amazon.com/console
```

We have used your public key to [encrypt](https://linux.die.net/man/1/rsautl) your AWS user credentials file. To read the credentials file, you must first decrypt the file with your private key, using the following command:

```bash
openssl rsautl -decrypt -inkey ~/.ssh/id_rsa -in encrypted_credentials.csv -out credentials.csv
```

## Using Credentials for AWS CLI

You will need your user's credentials to access the [AWS Command Line Interface (CLI)](https://aws.amazon.com/cli/). Best practice strongly suggests you set required AWS user credentials as local environment variables. For example, you can [source](http://stackoverflow.com/a/5228470/580268) these values, using a `.env` file. For example (replace with your credentials):

```bash
cat USER_C982F9C1D628.env
```

```bash
export AWS_ACCESS_KEY_ID="IKAFKSJ2XADWLCH63IV3"
export AWS_SECRET_ACCESS_KEY="w4oGvn2EA9L3Lr37iyOYAQXByHeJ6l2PPH8Xkvp9"
```

```bash
source USER_C982F9C1D628.env
```

## Randomized User ID

To conceal your identity from other candidates on AWS, ThoughtWorks has generated a random user ID (i.e. `USER_C982F9C1D628`). You should tag your AWS infrastructure with this user ID.

## AWS Web Console

You may use your user credentials to access to the [AWS Web Console](https://aws.amazon.com/console/). Use the 'Console login link' in the decrypted `credentials.csv` file. For example:

```text
https://521292340873.signin.aws.amazon.com/console
```

You will be asked to change your IAM user's password on your first login.

## Available AWS Services

Your AWS IAM User account provides access to provision and manage [Amazon EC2 instances](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Instances.html). Your account also provides access to the [EC2 Container Service (ECS)](https://aws.amazon.com/ecs/). If you require access to additional services to complete the test, please let us know.