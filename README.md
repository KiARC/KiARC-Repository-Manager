# KiARC Repository Manager
## What is this?
This is a GitHub action that can help you keep a repository in order! It supports both automated ToDo List generation and code formatting (via [Google Java Format](https://github.com/google/google-java-format)) for Java files at the moment.
## Usage
Add this to your repository as `.github/workflows/KiARC Repository Manager.yml`, or just the `kiarc-repository-manager` job to an existing workflow:
```yaml
name: KiARC Repository Manager

on: [push, pull_request]
jobs:
  kiarc-repository-manager:
    name: KiARC Repository Manager
    runs-on: ubuntu-latest
    steps:
      - uses: KiARC/KiARC-Repository-Manager@main
        with:
          # Config
```
## Configuration Options
| Name                    | Values (First is default)                  | Description                                                                                                                                                                               |
|-------------------------|--------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `generate-tdl`          | `true`,`false`                             | If `true`, the action will generate a  `todolist.txt`  in the root of your repository with a list of all the todo's it could find in Java files in the repository (or `tdlg-path` if set) |
| `tdlg-path`             | `./`,`a string`                            | The path for the todo list generator (keep in mind that subdirectories will be included)                                                                                                  |
| `tdlg-commit-message`   | `Automated ToDo List Generator`,`a string` | The message for the todo list commit                                                                                                                                                      |
| `format-code`           | `true`,`false`                             | If `true`, the action will format all Java code in the repository (or `format-path` if set) using `google-java-format`                                                                    |
| `format-path`           | `./`,`a string`                            | The path for the code formatter (keep in mind that subdirectories will be included)                                                                                                       |
| `format-commit-message` | `Automated Code Formatting`,`a string`     | The message for the code formatting commit                                                                                                                                                |
