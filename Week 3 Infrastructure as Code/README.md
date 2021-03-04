# Week 3 Infrastructure as Code

The code found in this repository is to help you learn and use Infrastructure as Code.

## Prepare Your DEV Environment

Things needed to install for these labs:

### VS Code & ARM
| Name                                    | Installation Method    | Install Command                                    |
| ----------------------------------------| -----------------------| ---------------------------------------------------|
| VS Code                                 | Download & Install     | [Download here](https://code.visualstudio.com/)    |
| Azure Resource Manager (ARM) Tools      | VS Code extension      | Install in VS Code                                 |
| ARM Template Viewer                     | VS Code extension      | Install in VS Code                                 |


### Terraform

| Name                      | Installation Method    | Install Command                                              |
| ------------------------  | ---------------------- | -----------------------------------------------------------  |
| Terraform                 | Download & Install     | [Download here](https://www.terraform.io/downloads.html)     |
| Terraform                 | VS Code extension      | Install in VS Code                                           |
| Hashicorp<br /> Terraform | VS Code extension      | Install in VS Code                                           |
| Go                        | Download & Install     | [Download here](hhttps://golang.org/dl/)                     |
| Go                        | VS Code extension      | Install in VS Code                                           |
| Go-Outline                | Go                     | `go get -v github.com/ramya-rao-a/go-outline`                |
| Go-Delve                  | Go                     | `go get -v github.com/go-delve/delve/cmd/dlv`                |

### Azure Bicep

| Name          | Installation Method    | Install Command                                                                 |
| --------------| -----------------------| --------------------------------------------------------------------------------|
| Bicep CLI     | Download & Install     | [Download here](https://github.com/Azure/bicep/blob/main/docs/installing.md)    |
| Bicep         | VS Code extension      | Install in VS Code                                                              |

## ARM code (template)

The ARM template found in `Week 3 Infrastructure as Code` is for anyone that wants to create a VNET, VM and Storage account in Azure.

## How to use the ARM template

To deploy the ARM template and create all the resources defined in it, run the following commands:

1. Login with Azure CLI
```
az login
```

2. Deploy the template (Existing Resource-Group required)
```
az deployment group create --resource-group cloudskillsbootcamp --template-file .\template.json
```

## Terraform code

The Terraform code found in `Week 3 Infrastructure as Code` is for anyone that wants to create an EC2 instance in AWS.

## How to use the Terraform code

1. Configure AWS (IAM access key and secret needed)
```
aws configure
```

2. Initialize the working directory with the Terraform configuration files "main.tf" under the Terraform directory.
```
Terraform init
```

3. Deploy the Terraform code
```
Terraform deploy
```

4. (Optional) Destroy configuration in AWS
```
Terraform destroy
```

## Testing

Terraform has an included test available under the Testing directory. Commands needed to be run before you can use the test: (Either in the "terraform-aws-webserver" root-folder or the "test" sub-folder)

1. Initialize go modules
```
go mod init terraform-aws-webserver
```

2. Download module dependencies
```
go mod tidy
```

3. Run test of the Terraform module
```
go test -v .\webserver_test.g
```

## Azure Bicep code

The Azure Bicep code found in `Week 3 Infrastructure as Code` is for anyone that wants to create a Storage account in Azure.

## How to use the Azure Bicep code

To deploy the Bicep template and create the storage account defined in it, run the following commands:

1. Login with Azure CLI
```
az login
```

2. Create ARM template based on the Biceps template
```
bicep build .\main.bicep
```

3. Deploy the ARM template generated out of the Biceps template (Existing Resource-Group required)
```
az deployment group create --recourse-group cloudskillsbootcamp --template-file .\main.json -p name=sa354-cloudskillsbootcamp
```

## Contributors

1. Besart Sulejmani
