# draft-scipy-2024-proceedings-submission
Draft version of SciPy 2024 proceedings submission

## Timeline

| Date | Event | Passed (✅/❌) |
| -    | :-    | -              |
| May 31   | Deadline to submit first draft by authors | 🎯 |
| May 31   | Open Review Period begins                 |  |
| June 21  | Initial complete review                   |  |
| July 26  | Final review deadline                     |  |
| July 31  | Final author revision deadline            |  |
| August 9 | Final reviewer decision deadline          |  |

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
