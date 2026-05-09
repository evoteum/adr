[//]: # (STANDARD README)
[//]: # (https://github.com/RichardLitt/standard-readme)
[//]: # (----------------------------------------------)
[//]: # (Uncomment optional sections as required)
[//]: # (----------------------------------------------)

[//]: # (Title)
[//]: # (Match repository name)
[//]: # (REQUIRED)

# adr

[//]: # (Banner)
[//]: # (OPTIONAL)
[//]: # (Must not have its own title)
[//]: # (Must link to local image in current repository)



[//]: # (Badges)
[//]: # (OPTIONAL)
[//]: # (Must not have its own title)



[//]: # (Short description)
[//]: # (REQUIRED)
[//]: # (An overview of the intentions of this repo)
[//]: # (Must not have its own title)
[//]: # (Must be less than 120 characters)
[//]: # (Must match GitHub's description)

CLI to manage Architecture Decision Records

[//]: # (Long Description)
[//]: # (OPTIONAL)
[//]: # (Must not have its own title)
[//]: # (A detailed description of the repo)

As defined by Michael Nygard in the 2011 article
[Documenting Architecture Decisions](https://www.cognitect.com/blog/2011/11/15/documenting-architecture-decisions),

> An architecture decision record is a short text file in a format similar to an 
> Alexandrian pattern.

Decision records are of vital importance as they prevent the, "We have always done 
it this way," problem. They allow teams to reassess whether a decision is still 
valid or whether a different option might be more appropriate.

The format can also be extended beyond architecture decisions by treating ADR as
"All Decision Records", allowing all teams to capture other important decisions using
the same lightweight structure.

ADRs are often underutilised in practice, so this CLI, along with the included
templates, aims to make them easier to create and maintain.

## Table of Contents

[//]: # (REQUIRED)
[//]: # (Managed automatically)
[//]: # (Changes between the TABLE_OF_CONTENTS_START and TABLE_OF_CONTENTS_END markers will be overritten)

[//]: # (TOCGEN_TABLE_OF_CONTENTS_START)

- [Install](#install)
- [Usage](#usage)
    - [Getting started](#getting-started)
    - [Templates](#templates)
        - [Nygard](#nygard)
        - [Extended](#extended)
    - [Configuration](#configuration)
    - [Commands](#commands)
- [Documentation](#documentation)
- [Repository Configuration](#repository-configuration)
- [Contributing](#contributing)
- [License](#license)
    - [Code](#code)
    - [Non-code content](#non-code-content)

[//]: # (TOCGEN_TABLE_OF_CONTENTS_END)

[//]: # (## Security)
[//]: # (OPTIONAL)
[//]: # (May go here if it is important to highlight security concerns.)



[//]: # (## Background)
[//]: # (OPTIONAL)
[//]: # (Explain the motivation and abstract dependencies for this repo)



## Install

[//]: # (Explain how to install the thing.)
[//]: # (OPTIONAL IF documentation repo)
[//]: # (ELSE REQUIRED)

This will be available via all good ~~bookshops~~ package management tools.

## Usage
[//]: # (REQUIRED)
[//]: # (Explain what the thing does. Use screenshots and/or videos.)

### Getting started

`adr init`

- Creates an empty `.adr.yaml` in repo root
- Adds an ADR documenting the decision to use ADRs in `docs/adr`

This is idempotent, so re-running when the files already exist will do nothing.

### Templates

#### Nygard
The `nygard` template directly follows the recommendations set out in
[DAD](https://www.cognitect.com/blog/2011/11/15/documenting-architecture-decisions).
It also includes section descriptions from the article verbatim.

#### Extended
The `extended` template extends the original format with additional subsections and 
descriptions to help you write high context ADRs. Takes a bit of extra 
work, but your future colleagues, and your future self, will be grateful.

We did not want to go full [927](https://xkcd.com/927/) on this, so have stuck with
the default of the `nygard` template. Nonetheless, in our experience, the extended
template does offer more long term value, while staying within the spirit of the
`nygard` recommendations.


### Configuration

In `.adr.yaml`, you can set,

| Setting         | Description                                         | Default    | Valid options          | Recommended option  |
|-----------------|-----------------------------------------------------|------------|------------------------|---------------------|
| `directory`     | The directory where ADRs will be stored             | `docs/adr` | Any directory path     | default             |
| `templateName`  | The name of the template that you wish to use       | `nygard`   | `nygard`, `extended`   | `extended`          |
| `sequenceWidth` | The number of digits to use in the sequence number. | `4`        | positive integer       | default             |
| `remoteConfig`  | shared remote config                                | empty      | any git file reference | use a remote config |

Remote config allows you to set one config for your entire repo estate in a central 
repo. It should be a `.yaml` file for clarity,  but `adr` will read whatever file 
you set, assuming it is valid YAML and the keys are valid. Local config overrides 
remote config.


For backwards compatibility, if you already have a `.adr-dir` file, you can continue 
using it. You can set,

| Setting       | Description                                                                                   | Default   | Valid options      | Recommended option         |
|---------------|-----------------------------------------------------------------------------------------------|-----------|--------------------|----------------------------|
| File contents | The directory where ADRs will be stored. The `directory` value in .adr.yaml takes precedence. | `doc/adr` | Any directory path | `directory` in `.adr.yaml` |


### Commands

`adr new Use the Turbo Encabulator`

This will create a new ADR named

`docs/adr/0023-use-the-turbo-encabulator.md`

The general filename convention is 

`[adr dir]/[sequence]-[title].md`

[//]: # (Extra sections)
[//]: # (OPTIONAL)
[//]: # (This should not be called "Extra Sections".)
[//]: # (This is a space for ≥0 sections to be included,)
[//]: # (each of which must have their own titles.)



## Documentation

Further documentation is in the [`docs`](docs/) directory.

## Repository Configuration

> [!WARNING]
> This repo is controlled by OpenTofu in the [estate-repos](https://github.com/evoteum/estate-repos) repository.
>
> Manual configuration changes will be overwritten the next time OpenTofu runs.


[//]: # (## API)
[//]: # (OPTIONAL)
[//]: # (Describe exported functions and objects)



[//]: # (## Maintainers)
[//]: # (OPTIONAL)
[//]: # (List maintainers for this repository)
[//]: # (along with one way of contacting them - GitHub link or email.)



[//]: # (## Thanks)
[//]: # (OPTIONAL)
[//]: # (State anyone or anything that significantly)
[//]: # (helped with the development of this project)



## Contributing
[//]: # (REQUIRED)
If you need any help, please log an issue and one of our team will get back to you.

PRs are welcome.


## License
[//]: # (REQUIRED)

### Code

All source code in this repository is licenced under the 
[GNU Affero General Public License v3.0 (AGPL-3.0)](https://www.gnu.org/licenses/agpl-3.0.en.html). A
copy of this is provided in the [LICENSE](LICENSE).

### Non-code content

All non-code content in this repository, including but not limited to images, diagrams or prose documentation, is
licenced under the
[Creative Commons Attribution-ShareAlike 4.0 International](https://creativecommons.org/licenses/by-sa/4.0/) licence.
