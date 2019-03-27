
# Calculator Specs
The Windows Calculator app is a modern Windows app written in C++ that ships pre-installed with Windows. This repository contains in-progress and archived spec documents for new features in [Microsoft/calculator](https://github.com/Microsoft/calculator).

Documents in this repo are used for features in development and are not intended to be up-to-date developer or user documentation. For product issues, bugs, and feature requests please go to [Microsoft/calculator](https://github.com/Microsoft/calculator).

## Contributing
We welcome your contributions to the project, and we thank you for your interest in making Calculator better! We follow a [user-centered process for developing features](https://github.com/Microsoft/calculator/blob/master/docs/NewFeatureProcess.md).
* **DO** provide feedback on **active pull requests**, which represent new features that are being reviewed
* **DO** provide feedback on spec documents in the `active` folder, which represent new features that are being worked on
* **DO NOT** provide feedback on spec documents in the `archive` folder since those features have already been released
* **DO NOT** submit pull requests that create new specs for ideas that do not have an associated approved feature pitch tracked in [Microsoft/calculator](https://github.com/Microsoft/calculator). To propose a new feature, please follow the Calculator [contribution process](https://github.com/Microsoft/calculator/blob/master/CONTRIBUTING.md)

### Workflow
 
1. Ensure that your pitch has been approved and moved into [pre-production](https://github.com/Microsoft/calculator/projects/1). When features enter this stage, a new working branch in this repo will be created: `feature/<feature>`

2. Create a new directory for your spec under the `active` directory: `/active/<feature>`

3. Write your spec following the [spec template](./spec_template.md), leveraging relative links when referencing images or other assets in the directory

4. When your spec is ready for review, open a new pull request to merge your spec into the `master` branch

5. Once all feedback has been addressed and your spec has been merged into `master`, your feature will move into [production](https://github.com/Microsoft/calculator/projects/1).

6. After your feature ships, move your spec from `active` to `archive`

## Contributor License Agreement

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.microsoft.com.

When you submit a pull request, a CLA-bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., label, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Legal Notices

Microsoft and any contributors grant you a license to the Microsoft documentation and other content
in this repository under the [Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode),
see the [LICENSE](LICENSE) file, and grant you a license to any code in the repository under the [MIT License](https://opensource.org/licenses/MIT), see the
[LICENSE-CODE](LICENSE-CODE) file.

Microsoft, Windows, Microsoft Azure and/or other Microsoft products and services referenced in the documentation
may be either trademarks or registered trademarks of Microsoft in the United States and/or other countries.
The licenses for this project do not grant you rights to use any Microsoft names, logos, or trademarks.
Microsoft's general trademark guidelines can be found at http://go.microsoft.com/fwlink/?LinkID=254653.

Privacy information can be found at https://privacy.microsoft.com/en-us/

Microsoft and any contributors reserve all other rights, whether under their respective copyrights, patents,
or trademarks, whether by implication, estoppel or otherwise.
