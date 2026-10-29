# UiPath Data-Input Automation

A UiPath automation example that reads rows from an Excel workbook, enters them into a companion C# desktop application, and reports completion or exceptions by email.

The companion [DataInputsRPATraining application](https://github.com/TonyJimenezDev/DataInputsRPATraining) was built as an example target for this workflow.

## Workflow

1. Read the configured Excel input.
2. Use each row to populate the training application.
3. Report completed rows or exceptions through the configured email route.

This repository demonstrates desktop automation and its relationship to an application designed for practice. It is not a claim of a production deployment or measured business savings.

## Project structure

- `Main.xaml`: workflow entry point
- `Process.xaml` and `ProcessingData/`: processing workflows
- `Framework/`: framework workflows
- `Data/`: project data and configuration material
- `Documentation/`: supporting project documentation
- `Tests/`: existing workflow test material; execution has not been verified in this documentation update
- `project.json`: project metadata and activity dependencies

## Environment

The checked-in metadata records UiPath Studio 21.6.0.0 and a Legacy target framework. Workflow expressions are Visual Basic; the companion desktop application is C#.

Activity dependencies are declared in `project.json`, including Excel, Mail, System, and UI Automation activities. One recorded UI Automation dependency is a preview version. Compatibility with a current UiPath installation requires validation rather than an assumption that the historical project runs unchanged.

## Setup and configuration

1. Review the workflow and configuration using synthetic example data.
2. Build and run the companion Windows application in a compatible Windows environment.
3. Open this repository's `project.json` in a compatible UiPath Studio installation and restore the declared dependencies.
4. Inspect the configuration, application paths, selectors, and workbook format before running.
5. Set `EmailTo` and `EmailChoice` in the configuration. The original instructions specify `EmailChoice = 1` for the web-email route when the Outlook desktop application is unavailable. That route expects an already signed-in browser session.
6. Review the email activities and choose a test recipient you control before executing `Main.xaml`.

Do not commit live credentials, real customer records, or employer/client information. The presence of checked-in example files does not establish that every file has been reviewed for public reuse.

## Limitations and validation

Desktop selectors, application paths, browser sessions, and email integrations depend on the local environment. A repeatable demonstration and current dependency compatibility remain to be verified. No new test results, reliability figures, or performance claims are asserted by this README.
