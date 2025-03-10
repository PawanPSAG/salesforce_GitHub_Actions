# salesforce_GitHub_Actions

Setting up a deployment pipeline from GitHub to a Salesforce Enviornment involves several steps

# Salesforce Creds

## Consumer Key

3MVG9KAEr0ABaqiqmuW0uSH8dhyCIFelpjrfN.THsaRCQLSNeClD_MwjxKn0uNLvAw7V3vMQyX.IgkST2BSqH

## Consumer Secret

E9D8AA140EB90B505750706A9FCEF56B41B09652949FC47613D09AF026E1E3AB

## Authenticate Using the Custom Port

sfdx auth:web:login --setalias pawandev --instanceurl https://test.salesforce.com

## Generate a private key

- openssl genrsa -out server.key 2048

## Verify the File Path

- cd /path/to/your/key

## Check if the file exists: server.key

- ls -l server.key

## Encode the file to base64

- base64 -i server.key

## If you want to save the output to a file

base64 -i server.key > server.key.base64

## Create a certificate

- openssl req -new -x509 -key server.key -out server.crt -days 365

## Authenticate Using JWT

- sfdx auth:jwt:grant --clientid <Consumer_Key> --jwtkeyfile server.key --username <Sandbox_Username> --instanceurl https://test.salesforce.com

eg : - sfdx auth:jwt:grant --clientid 3MVG9KAEr0ABaqiqmuW0uSH8dhyCIFelpjrfN.THsaRCQLSNeClD_MwjxKn0uNLvAw7V3vMQyX.IgkST2BSqH --jwtkeyfile server.key --username pawan.kumar@psagtechnologies.com.prod.pawandev --instanceurl https://test.salesforce.com
