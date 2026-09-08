## Требования к именам коммитов

- Названия коммитов должны соответствовать [спецификации Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)
- Спецификация допускает любой регистр типа, но он должен быть единообразным - в заданиях RS School принят **нижний** (`feat`, `fix`, `refactor`, `docs`, `style`, `test`, `perf`, `build`, `ci`, `chore` и т.д.)
- Должен использоваться present tense ("add feature" not "added feature")
- Должен использоваться imperative mood ("move cursor to..." not "moves cursor to...")

## Структура коммита

```
<тип>[необязательная область]: <описание>
```

- **тип** - обязателен, после него ставится двоеточие и пробел
- **область (scope)** - необязательное уточнение части кодовой базы, указывается в круглых скобках сразу после типа
- **описание** - краткое изложение изменений, следует сразу после двоеточия с пробелом

```
fix: prevent racing of requests
fix(parser): prevent racing of requests
```

Этого формата достаточно для учебных заданий. При желании можно использовать и дополнительные элементы спецификации - тело коммита, футеры (например, `Refs: #123`) и обозначение обратно несовместимых изменений (`feat!:` или футер `BREAKING CHANGE:`).

### Примеры имен коммитов

- `feat:` - это реализованная новая функциональность из технического задания (добавил поддержку зумирования, добавил footer, добавил карточку продукта). Примеры:

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

- `fix:` - исправил ошибку в ранее реализованной функциональности. Примеры:

```
fix: implement correct loading data from youtube
fix: change layout for video items to fix bugs
fix: relayout header for firefox
fix: adjust social links for mobile
fix: prevent array parsing issue when string contains multiple spaces
```

- `refactor:` - новой функциональности не добавлял/поведения не менял. Файлы в другие места положил, удалил, добавил. Улучшил алгоритм, без изменения функциональности. Примеры:

```
refactor: change structure of the project
refactor: rename vars for better readability
```

- `docs:` - используется при работе с документацией/readme проекта. Примеры:

```
docs: update readme with additional information
docs: update description of run() method
```

- `style:` - используется при изменениях стиля и оформления кода. Примеры:

```
style: remove trailing white spaces
style: add missing semi-colons
style: format code with prettier
```

- `test:` - используется при добавлении и исправлении тестов. Примеры:

```
test: add unit tests for search box
test: cover error handling in api client
```

- `perf:` - используется при изменениях, улучшающих производительность. Примеры:

```
perf: memoize expensive calculations in product list
perf: reduce bundle size by lazy loading routes
```

- `build:` - используется при изменениях в системе сборки и внешних зависимостях. Примеры:

```
build: update webpack config for production build
build: bump typescript to 5.4
```

- `ci:` - используется при изменениях в конфигурации и скриптах CI. Примеры:

```
ci: add github actions workflow for linting
ci: run tests on pull request
```

- `chore:` - используется, когда не меняются исходные файлы и файлы тестов. Примеры:

```
chore: add .editorconfig file for uniform code formatting
chore: rename environment variable file to .env.example
```

- `revert:` - используется для отката ранее сделанного коммита. Примеры:

```
revert: remove swipe support for horizontal list
revert: restore previous header layout
```

## FAQ

### Как оформлять коммиты на начальном этапе разработки? Нужен ли тип `init`?

Рекомендуется действовать так, как будто продукт уже выпущен. Как правило, кто-то уже пользуется вашим кодом - даже если это ваши коллеги-разработчики. Им важно знать, что исправлено, что перестало работать и т.д.

Поэтому отдельный тип `init` для начала работы над проектом не нужен - первые коммиты оформляются обычными `feat:`, `chore:` и т.д. Раньше этот тип упоминался в документации, поэтому его использование ошибкой не считается, но в спецификации его нет, и применять его не рекомендуется.

### Что делать, если случайно использован неправильный тип коммита?

- **Коммит ещё не запушен** - поправьте его локально: `git commit --amend` для последнего коммита, `git rebase -i` для более раннего.
- **Коммит уже в удалённой ветке, но работа не отправлена на проверку** - после правки истории обновите ветку командой `git push --force-with-lease`.
- **Работа уже отправлена на проверку** - историю переписывать не стоит: force-push отвязывает оставленные ревьюером комментарии от строк кода, а в случае cross-check изменения в работе после дедлайна лишают права на апелляцию. Учтите замечание в следующих коммитах и заданиях.

### Можно ли ревертнуть отправленный (запушенный) в репозиторий коммит без снижения оценки?

Да, можно.
