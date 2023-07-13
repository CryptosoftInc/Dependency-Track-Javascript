# Cryptosoft-SBOM-Javascript 

[![Website](https://img.shields.io/badge/https://-www.cryptosoft.com-blue.svg)](https://www.cryptosoft.com/)



# Introduction

This GitHub action will create a valid Software Bill-of-Materials (SBOM) containing an aggregate of all project dependencies and then will upload to OWASP Dependency-Track.


## Inputs

1) Dependency-Track url - required
2) Dependency-Track api-key - required
3) Project Name - required
4) Project Version - required
5) Parent Project Name - optional
6) Parent Project Version - optional


## Output
The default token output confirms that the SBOM has been successfully uploaded to Dependency-Track.

## Usage
```
uses: CryptosoftInc/Dependency-Track-Javascript@1.0.0
```

## To use this action, follow these steps:

1) Navigate to your GitHub project directory.
2) Create a new file named .github/workflows/file-name.yaml.
3) Copy the provided code snippet below and paste it into the newly created YAML file.

### Use below snippet for Javascript Projects
```
name: Your-Workflow-Name
on: push
jobs:
  myJob:
    runs-on: ubuntu-latest
    steps:
      - name: Cryptosoft-SBOM-Dependency-Track
        id: Cryptosoft-SBOM-Dependency-Track
        uses: CryptosoftInc/Dependency-Track-Javascript@1.0.0
        with:
          dt-url: <your dt url>
          # you can store api-key obtained in your github secrets. 
          api-key: ${{ secrets.apiKey }}
          project-name: <your project name>
          project-version: <your project version >
          # If you want to create a project under a parent project, use the below inputs
          # Please ensure you have a valid parent project existing in your Dependency-Track and provide the values for the below variables
          # Do not use the below variables if there is no parent project in your Dependency-Track
          parent-name: <your parent project name>
          parent-version: <your parent project version >
```
 
## Contribution

Suggestions are welcome!
