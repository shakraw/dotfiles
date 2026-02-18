# Magento 2 Module Development
[PROJECTNAME] — This is a Magento 2 composer module repository.

## Development Standards
- **Naming Conventions:**
  - Classes: CamelCase (e.g., `MyProcessor`).
  - Methods/Variables: camelCase (e.g., `processData`).
  - Tables/Columns: snake_case.
- **Coding Style:** 
  - Follow Magento Coding Standards (PSR-12).
  - Use short array syntax `[]` instead of `array()`
  - Order imports alphabetically and group by namespace
  - For dependencies, favor constructor injection, use type hints
  - Handle exceptions properly, never suppress or swallow them
  - Use PHP 8.1+ features where possible
  - Always use constructor property promotion
  - Always declare parameter types and return types in methods
  - Don't add return types to functions that need to abide by an interface (models, resource models, collections, etc.)
  - Always add proper type casting for integer returns in model classes:
    - For nullable integer fields: `return $this->getData(FIELD) ? (int) $this->getData(FIELD) : null;`
    - For required integer fields: `return (int) $this->getData(FIELD);`
  - Add line break to the end of files
  - Add @throws tags to docblocks for exceptions, where appropriate
  - Don't use trailing commaas for all arrays and method arguments
  - Import all classes with use statements rather than using FQCNs
  - Do not add copyright headers, but add line break and declare(strict_types=1) to top of each PHP class
  - Don't nest arrays on single line, always use multi-line format for readability
  - Always add extra line breaks between conditions and before return statements, unless only statement in block
  - Always add an extra line break after parent::__construct calls
  - Methods that contain one or no parameters break curly brackets onto a new line
  - Methods with multiple parameters should have parameters on new lines with trailing commas
  - Use Dependency Injection via `__construct`. Never use `ObjectManager` directly.
  - Use Plugins/Observers over Preferences to ensure cross-module compatibility; use `db_schema.xml` for database changes.

## Common Workflows
1. **Module Creation:** Create registration.php and etc/module.xml
