## Commit Requirements

- The names of the commits should follow the [Conventional Commits specification](https://www.conventionalcommits.org/en/v1.0.0/)
- The specification allows any casing of the type, but it should be consistent - RS School tasks use **lowercase** (`feat`, `fix`, `refactor`, `docs`, `style`, `test`, `perf`, `build`, `ci`, `chore` etc.)
- Present tense ("add feature" not "added feature") should be used
- Imperative mood ("move cursor to..." not "moves cursor to...") should be used

## Commit Structure

```
<type>[optional scope]: <description>
```

- **type** - required, followed by a colon and a space
- **scope** - an optional noun describing a section of the codebase, placed in parentheses right after the type
- **description** - a short summary of the changes, follows immediately after the colon and space

```
fix: prevent racing of requests
fix(parser): prevent racing of requests
```

This format is enough for the study tasks. If you want, you can also use the additional elements of the specification - a commit body, footers (for example, `Refs: #123`) and breaking change notation (`feat!:` or a `BREAKING CHANGE:` footer).

### Examples of commit names

- `feat:` - this is the implemented new functionality from the technical requirements (added zoom support, added footer, added product card). Examples:

```
feat: add basic page layout
feat: implement search box
feat: implement request to youtube API
feat: implement swipe for horizontal list
feat: add additional navigation button
feat: add banner
feat: add social links
feat: add physical security section
feat: add real social icons
```

- `fix:` - fixed a bug in previously implemented functionality. Examples:

```
fix: implement correct loading data from youtube
fix: change layout for video items to fix bugs
fix: relayout header for firefox
fix: adjust social links for mobile
fix: prevent array parsing issue when string contains multiple spaces
```

- `refactor:` - did not add new functionality/behavior did not change. Files in other places put, deleted, added. Improved the algorithm without changing the functionality. Examples:

```
refactor: change structure of the project
refactor: rename vars for better readability
```

- `docs:` - used when working with project documentation/readme. Examples:

```
docs: update readme with additional information
docs: update description of run() method
```

- `style:` - used for changes in code style and formatting. Examples:

```
style: remove trailing white spaces
style: add missing semi-colons
style: format code with prettier
```

- `test:` - used when adding or fixing tests. Examples:

```
test: add unit tests for search box
test: cover error handling in api client
```

- `perf:` - used for changes that improve performance. Examples:

```
perf: memoize expensive calculations in product list
perf: reduce bundle size by lazy loading routes
```

- `build:` - used for changes in the build system and external dependencies. Examples:

```
build: update webpack config for production build
build: bump typescript to 5.4
```

- `ci:` - used for changes in CI configuration and scripts. Examples:

```
ci: add github actions workflow for linting
ci: run tests on pull request
```

- `chore:` - used when neither source files nor test files are changed. Examples:

```
chore: add .editorconfig file for uniform code formatting
chore: rename environment variable file to .env.example
```

- `revert:` - used to revert a previous commit. Examples:

```
revert: remove swipe support for horizontal list
revert: restore previous header layout
```

## FAQ

### How should I deal with commit messages in the initial development phase? Is the `init` type needed?

We recommend that you proceed as if you've already released the product. Typically, somebody, even if it's your fellow software developers, is using your software. They'll want to know what's fixed, what breaks etc.

That is why a separate `init` type for starting the work on a project is not needed - the first commits use the regular `feat:`, `chore:` and so on. This type used to be mentioned in the documentation, so using it is not considered a mistake, but it is not part of the specification and is not recommended.

### What do I do if I accidentally use the wrong commit type?

- **The commit has not been pushed yet** - fix it locally: `git commit --amend` for the last commit, `git rebase -i` for an earlier one.
- **The commit is already in the remote branch, but the work has not been submitted for review** - after editing the history, update the branch with `git push --force-with-lease`.
- **The work has already been submitted for review** - it is better not to rewrite the history: a force-push detaches the reviewer's comments from the lines of code, and in case of a cross-check, changes made to your work after the deadline deprive you of the right to appeal. Take the remark into account in your next commits and tasks.

### Is it possible to reverse a commit (pushed) to a repository without reducing the score?

Yes, you can.
