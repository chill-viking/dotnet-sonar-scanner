# dotnet-sonar-scanner

<!-- TODO: add other status badges once workflows sorted out -->
![test pipelines](https://github.com/chill-viking/dotnet-sonar-scanner/actions/workflows/test-action.yml/badge.svg?branch=main)  
![release badge](https://img.shields.io/github/v/release/chill-viking/dotnet-sonar-scanner?display_name=release&logo=github&sort=semver)
<hr/>

GitHub Action to scan a dotnet project using sonar scanner.

<hr/>

This action will check out your code (by default) and execute `dotnet build` and `dotnet test` in the root directory.

This directory used can be changed by specifying the [input](#inputs) `working-directory`.

The directory used should have a single solution `.sln` file containing the projects being tested and optionally test projects to run against the projects.

## Supported .NET Frameworks

- .NET 6

> If you require a framework that is not listed and it does not current work, please log an issue.

## Usage

To use this GitHub Action, you will need to have a [SonarCloud](https://sonarcloud.io) organisation and project in
place.

You can follow the [documentation](https://docs.sonarcloud.io/getting-started/github/) to create a project.

### Example basic workflow:

```yaml
jobs:
  test_and_report_coverage:
    runs-on: ubuntu-latest
    name: dotnet test coverage update
    steps:
      - uses: chill-viking/dotnet-sonar-scanner@v1
        name: Scan and Publish
        with:
          sonar-project-key: '{sonar-project-key}'
          sonar-org-key: '{sonar-org-key}'
          token: ${{ secrets.GITHUB_TOKEN }}
          sonar-token: ${{ secrets.SONAR_TOKEN }}
```

With the above example, you will need to perform these steps:

1. Replace `{sonar-project-key}` with your SonarCloud project key
2. Replace `{sonar-org-key}` with your SonarCloud organisation key
3. [Create a repository secret](https://docs.github.com/en/actions/security-guides/encrypted-secrets#creating-encrypted-secrets-for-a-repository)
   using key provided by SonarCloud when creating your project. In the example above, this should be saved
   as `SONAR_TOKEN`

### Example mono-repo workflow:

The below example is based on the idea that the repo in use has a .NET project to scan
in folder `/src/dotnet-api`

```yaml
on:
   push:
      branches: [main]
      paths:
         - 'src/dotnet-api/**' # only run on changes in .NET code
   # should include pull_request trigger, but leaving out for simplicity here

jobs:
  test_and_report_coverage:
    runs-on: window-latest # can also run on windows-latest
    name: dotnet test coverage update
    steps:
      - uses: actions/checkout@v3
        with:
          fetch-depth: 0  # Shallow clones should be disabled for a better relevancy of analysis

      # preform additional steps with repo checked out

      - uses: chill-viking/dotnet-sonar-scanner@v1
        name: Scan and Publish
        with:
          sonar-project-key: '{sonar-project-key}'
          sonar-org-key: '{sonar-org-key}'
          token: ${{ secrets.GITHUB_TOKEN }}
          sonar-token: ${{ secrets.SONAR_TOKEN }}
          working-directory: './src/dotnet-api'
          checkout: false
```

Follow the same steps as mentioned in [basic workflow](#example-basic-workflow-) and your workflow should be good to test analyze your project in `/src/dotnet-api`

You can review an example repo using this kind of workflow [here](https://github.com/chill-viking/github-actions-tests)

## Inputs

| Input               | Required | Description                                                                             |
|:--------------------|:--------:|:----------------------------------------------------------------------------------------|
| `sonar-project-key` |   Yes    | SonarCloud project key                                                                  |
| `sonar-org-key`     |   Yes    | SonarCloud organization key                                                             |
| `token`             |   Yes    | GitHub token for the current workflow                                                   |
| `sonar-token`       |   Yes    | SonarCloud authentication token                                                         |
| `working-directory` |    No    | Specify location of primary solution to build and test in repo<br/>**default:** `./`    |
| `dotnet-version`    |    No    | .NET SDK version to be used<br/>**default:** `6.0.x`                                    |
| `project-version`   |    No    | Version of project being scanned, will be set in analysis<br/>**default:** `''`         |
| `checkout`          |    No    | Flag to inform action whether it should check out repo or not<br/>**default:** `true`   |

<hr/>

Total views: [![HitCount](https://hits.dwyl.com/chill-viking/dotnet-sonar-scanner.svg?style=flat-square)](http://hits.dwyl.com/chill-viking/dotnet-sonar-scanner)
