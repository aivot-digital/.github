<p align="center">
  <a href="https://aivot.de" target="_blank"><img width="150" src="https://aivot.de/img/aivot-logo.svg" alt="Aivot logo"></a>
</p>

<h1 align="center">GitHub default (community health) files</h1>

<p>The default (community health) files for every project at <a href="https://aivot.de" target="_blank">Aivot</a> are maintained here. The default community health files are based on the <a href="https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file" target="_blank">GitHub docs.</a></p>

# Community health files
Overview over the community health files used by us and how they find their way into our projects.

| Community health file                                          | Integration                                                                          | Customizations           | based on template                                                                               |
|----------------------------------------------------------------|--------------------------------------------------------------------------------------|--------------------------|-------------------------------------------------------------------------------------------------|
| [CODE_OF_CONDUCT.md](./docs/CODE_OF_CONDUCT.md)                | Automatically via .github repository (unless specifically overwritten by repository) | No customizations needed | Based on [this](https://www.contributor-covenant.org/version/2/1/code_of_conduct.html) template |
| [CONTRIBUTING.md](./docs/CONTRIBUTING.md)                      | Automatically via .github repository (unless specifically overwritten by repository) | No customizations needed | Not based on a template                                                                         |
| [GOVERNANCE.md](./docs/GOVERNANCE.md)                          | Automatically via .github repository (unless specifically overwritten by repository) | No customizations needed | Not based on a template                                                                         |
| [ISSUE_TEMPLATES and config.yml](./.github/ISSUE_TEMPLATE)     | Automatically via .github repository (unless specifically overwritten by repository) | No customizations needed | The issue templates in this directory follow the respective templates defined in Clickup.       |
| [PULL_REQUEST_TEMPLATE.md](./.github/PULL_REQUEST_TEMPLATE.md) | Automatically via .github repository (unless specifically overwritten by repository) | No customizations needed | The issue templates in this directory follow the respective templates defined in Clickup.       |
| [SECURITY.md](./docs/SECURITY.md)                              | Automatically via .github repository (unless specifically overwritten by repository) | No customizations needed | Not based on a template                                                                         |

## Community health files that aren't used

**Discussion category forms:** Currently we don't use the discussions feature of GitHub.

**FUNDING.yml:** Since we mainly follow the principle of Fair-Code, we reserve the right of commercialization. Therefore we refrain from donations.

**SUPPORT.md:** We use the [config.yml](./.github/ISSUE_TEMPLATE/config.yml) to configure the support option.




# Miscellaneous
Overview over miscellaneous files for licensing, information etc. commonly used in our projects.  
For licensing purposes, the licenses listed here are permitted for our own repositories. The appropriate license must be determined on a case-by-case basis.

| File                                                                             | Integration                                             | Customizations                                           | based on template                                                              |
|--------------------------------------------------------------------------------- |---------------------------------------------------------|----------------------------------------------------------|--------------------------------------------------------------------------------|
| [CHANGELOG.md](./templates/CHANGELOG.md)                                         | Needs to be manually added to the project               | Contains (automatically generated) changelog information | Not based on a template                                                        |
| [CONTRIBUTOR_LICENSE_AGREEMENT.md](./templates/CONTRIBUTOR_LICENSE_AGREEMENT.md) | Needs to be manually added to the project               | No customization needed                                  | Based on [this](https://indieopensource.com/forms/cla) template                |
| [LICENSE_SUL.md](./templates/LICENSE_SUL.md)                                     | Needs to be manually added to the project as LICENSE.md | No customization needed                                  | Based on [this](https://github.com/n8n-io/n8n/blob/master/LICENSE.md) template |
| [LICENSE_AGPL3.md](./templates/LICENSE_AGPL3.md)                                 | Needs to be manually added to the project as LICENSE.md | No customization needed                                  | Based on [this](https://www.gnu.org/licenses/agpl-3.0.txt) template            |
| [LICENSE_MIT.md](./templates/LICENSE_MIT.md)                                     | Needs to be manually added to the project as LICENSE.md | Add year                                                 | Based on [this](https://opensource.org/license/mit) template                   |
| [README.md](./templates/README.md)                                               | Needs to be manually added to the project               | Customization needed                                     | Not based on a template                                                        |
| [STYLEGUIDE.md](./templates/STYLEGUIDE.md)                                       | Needs to be manually added to the project               | Customization needed                                     | Not based on a template                                                        |