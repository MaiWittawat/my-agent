# Coding Conventions Review

Review the current code against our project conventions and flag any violations.

## Check these conventions:

### Naming
- [ ] Files follow [NAMING_CONVENTION] convention
- [ ] Functions/methods use [NAMING_CONVENTION]
- [ ] Variables use [NAMING_CONVENTION]
- [ ] Types/interfaces use [NAMING_CONVENTION]

### Code Style
- [ ] [MAX_LINE_LENGTH] character line limit
- [ ] [INDENT_STYLE] indentation ([INDENT_SIZE] spaces / tabs)
- [ ] Imports are organized: [IMPORT_ORDER]
- [ ] No unused imports or variables
- [ ] No `any` types / untyped variables

### Patterns
- [ ] Error handling follows [ERROR_PATTERN] pattern
- [ ] Logging uses [LOGGER] (not console.log / fmt.Println)
- [ ] Database queries go through [ORM/REPOSITORY_LAYER]
- [ ] Business logic lives in [SERVICE_LAYER], not in [HANDLER_LAYER]
- [ ] Input validation at [VALIDATION_LAYER]

### Testing
- [ ] New functions have corresponding tests
- [ ] Test files follow [TEST_FILE_PATTERN] pattern
- [ ] Tests use [TEST_FRAMEWORK]
- [ ] Mocking follows [MOCK_PATTERN]

## Instructions

1. Read the changed files (use `git diff` to find them)
2. Check each file against the conventions above
3. Report violations grouped by file
4. Suggest fixes for each violation
5. If no violations found, confirm compliance
