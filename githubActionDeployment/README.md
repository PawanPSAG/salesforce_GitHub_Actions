# Salesforce DX Project: Next Steps

Now that you’ve created a Salesforce DX project, what’s next? Here are some documentation resources to get you started.

## How Do You Plan to Deploy Your Changes?

Do you want to deploy a set of changes, or create a self-contained application? Choose a [development model](https://developer.salesforce.com/tools/vscode/en/user-guide/development-models).

## Configure Your Salesforce DX Project

The `sfdx-project.json` file contains useful configuration information for your project. See [Salesforce DX Project Configuration](https://developer.salesforce.com/docs/atlas.en-us.sfdx_dev.meta/sfdx_dev/sfdx_dev_ws_config.htm) in the _Salesforce DX Developer Guide_ for details about this file.

## Read All About It

- [Salesforce Extensions Documentation](https://developer.salesforce.com/tools/vscode/)
- [Salesforce CLI Setup Guide](https://developer.salesforce.com/docs/atlas.en-us.sfdx_setup.meta/sfdx_setup/sfdx_setup_intro.htm)
- [Salesforce DX Developer Guide](https://developer.salesforce.com/docs/atlas.en-us.sfdx_dev.meta/sfdx_dev/sfdx_dev_intro.htm)
- [Salesforce CLI Command Reference](https://developer.salesforce.com/docs/atlas.en-us.sfdx_cli_reference.meta/sfdx_cli_reference/cli_reference.htm)

## Salesforce Creds 
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