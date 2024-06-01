# draft-scipy-2024-proceedings-submission
Draft version of SciPy 2024 proceedings submission


To submit to SciPy, Matthew Feickert will open a PR to the [SciPy proceedings](https://github.com/scipy-conference/scipy_proceedings/tree/2024) with the contents of the `paper/` directory of this repository.

* Word limit: 6000 words

## Timeline

SciPy 2024 Proceedings PR: https://github.com/scipy-conference/scipy_proceedings/pull/924

| Date | Event | Passed (✅/❌) |
| -    | :-    | -              |
| May 31   | Deadline to submit first draft by authors | 🎯 |
| May 31   | Open Review Period begins                 |  |
| June 21  | Initial complete review                   |  |
| July 26  | Final review deadline                     |  |
| July 31  | Final author revision deadline            |  |
| August 9 | Final reviewer decision deadline          |  |

## [General Information and Guidelines for Authors](https://github.com/scipy-conference/scipy_proceedings/tree/2024?tab=readme-ov-file#general-information-and-guidelines-for-authors)

- The paper is written and reviewed using the interactive HTML view (i.e. `myst start`), the PDF is built upon acceptance only
- Example papers are provided in `papers/00_myst_template`
  - These papers provide examples of how to:
    - Label figures, equations and tables
    - Use math markup
    - Include code snippets
    - Use a BibTeX files and/or DOIs for citations
- When creating your pull-request, add a pull-request label of `paper` to trigger the build process. If you do not add this, a proceedings chair member will add it for you.
- Authors may include a project or consortium (e.g. [The Jupyter Project](https://raw.githubusercontent.com/scipy-conference/scipy_proceedings/2018/papers/project_jupyter/paper.rst))
- There must be at least one corresponding author, and this must be a specific person with a valid email address
- Authors of papers from previous SciPys may change their name on their published work by contacting the Proceedings Co-chairs
- All citations that have DOIs should include those DOIs in the paper's references section, see [`mybib.bib`](https://github.com/scipy-conference/scipy_proceedings/blob/2024/papers/00_myst_template/mybib.bib).
- All figures and tables should have captions.
- Figures and tables should be positioned close to their explanatory text.
- All abbreviations should be identified in your `myst.yml` ([docs](https://mystmd.org/guide/glossaries-and-terms#abbreviations))
- License conditions on images and figures must be respected (Creative Commons,
  etc.)
- Images and figures should be reasonably sized and formatted for viewing online; typically less than 1 MB
- Do not modify any files outside of your paper directory
- The compiled version of the paper should be at most 6000 words

including figures but not including references; this is about 8 pages for the published PDF that will be created upon acceptance.

## Development instructions

These are just following the [SciPy 2024 "Instructions for Authors" instructions](https://github.com/scipy-conference/scipy_proceedings/tree/2024?tab=readme-ov-file#instructions-for-authors) with additional information on using `pixi`.

### Writing with `pixi`

Follow the [`pixi` install instructions](https://pixi.sh/latest/#installation) and then you're ready to use `pixi` across Linux, macOS, Windows.

To render the paper draft while working on it, from the top level of this repository run

```console
pixi run build
```

which will then install any dependencies not yet installed from the lock file, run the build commands, and then present you a `localhost` URL where the paper is rendered live.
Open the URL in a web browser, and then write in the paper source files (e.g. `paper/myst.md`, `paper/myst.yml`, `paper/mybib.bib`). The browser view will update on save of the files.

If you would like to work in an interactive environment where the `dev` dependencies are also installed run

```console
pixi shell -e dev
```

and then continue as described above.

#### PDF export

To build a PDF render of the paper using a local install of LaTeX run

```console
pixi run export-pdf
```

which will create LaTeX files and build `paper/exports/scipy_proceedings_draft.pdf`.

### Writing collectively

For this document, the authors will write collectively via pull requests.
This will require some degree of coordination, so please communicate freely with each other on the IRIS-HEP Slack.
To avoid creating noisy diffs **do not** merge any PR that does not pass pre-commit.ci.
