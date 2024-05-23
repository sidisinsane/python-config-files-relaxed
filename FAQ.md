# FAQ

## What is the Python package manager / workflow tool of my choice?

Tl;dr: [**`Hatch`**](https://hatch.pypa.io/latest/).

Let me start off by quoting [Adam Hill](https://dev.to/adamghill) in his post “[Python Package Manager Comparison](https://dev.to/adamghill/python-package-manager-comparison-1g98)“ from Nov 15, 2023 in the [DEV Community](https://dev.to/).

> [...] `Python` packaging seems to be going through a new era of innovation. `pip` [released a dependency resolver in 2020](https://pip.pypa.io/en/latest/user_guide/#changes-to-the-pip-dependency-resolver-in-20-3-2020) that now complains when dependencies conflict. Also in 2020, [PEP 621](https://peps.python.org/pep-0621/) and [PEP 631](https://peps.python.org/pep-0631/) standardized `pyproject.toml` as the new normal for Python packages instead of `setup.py`. [PEP 517](https://peps.python.org/pep-0517/) and [PEP 660](https://peps.python.org/pep-0660/) created standards for Python build systems.
> 
> Based on those PEPs, `Poetry` isn't the only forward-thinking package manager anymore. `pipenv` is still around (and I presume more stable at this point!), but [`Hatch`](https://hatch.pypa.io/), [`PDM`](https://pdm-project.org/), and [`Rye`](https://rye-up.com/) all promise a pleasant developer experience when creating Python packages.

In short, many choices and many potential annoyances.
So, these are my prioritized requirements for a Python Package Manager / Workflow Tool:

- Living project with decent documentation and community.
- Straight forward setup.
- Virtual environments within the project directory.
- Compliance with the Python PEP standards.

Contenders I have worked with:

- [`Pipenv`](https://pipenv.pypa.io/en/latest/)
- [`Setuptools`](https://setuptools.pypa.io/en/latest/userguide/)
- [`Poetry`](https://python-poetry.org/)
- [`PDM`](https://pdm-project.org/en/latest/)
- [`Hatch`](https://hatch.pypa.io/latest/)
- [`Rye`](https://github.com/astral-sh/rye)

And the winner is [**`Hatch`**](https://hatch.pypa.io/latest/)! [`Rye`](https://github.com/astral-sh/rye) is a close runner-up and a project to look out for.

## How do the Google and PEP 8 coding style guides compare?

Google's Python Style Guide and PEP 8 both provide guidelines for writing clean, readable, and consistent Python code, but there are some key differences between them. Here's a comparison:

### Similarities

1. **Code Readability**: Both guides prioritize code readability and consistency.
2. **Line Length**: Both recommend a maximum line length of 80 characters.
3. **Indentation**: Both use 4 spaces per indentation level.
4. **Whitespace**: Both have rules on the use of whitespace in expressions and statements to improve readability.
5. **Comments and Docstrings**: Both emphasize the importance of comments and docstrings for code documentation and use PEP 257 conventions for docstrings.

### Differences

1. **Imports**:
   
   - **PEP 8**: Recommends grouping imports in the following order: standard library imports, related third-party imports, and local application/library-specific imports. Each group should be separated by a blank line.
   - **Google**: Has a stricter order for imports: standard library imports, third-party imports, application-specific imports. Additionally, Google’s guide includes more detailed rules about importing individual attributes and functions instead of the entire module.

2. **String Quotes**:
   
   - **PEP 8**: Does not mandate a specific quote style but advises consistency within a project.
   - **Google**: Prefers double quotes for strings (“”) and single quotes for single-character strings.

3. **Line Breaks**:
   
   - **PEP 8**: Encourages breaking long lines inside parentheses, brackets, or braces.
   - **Google**: Strongly discourages backslashes for line continuation and prefers using parentheses.

4. **Docstrings**:
   
   - **PEP 8**: Follows PEP 257 and suggests triple double quotes for docstrings.
   - **Google**: Also follows PEP 257 but has a more detailed section on the structure of docstrings, especially for classes and functions, and recommends including types in the docstrings.

5. **Naming Conventions**:
   
   - **PEP 8**: Provides detailed guidelines for naming conventions (e.g., variables, function names should be lower_case_with_underscores, classes should be in CapitalizedWords).
   - **Google**: Similar to PEP 8 but also includes conventions for global variable names (with a g_ prefix) and constants (all caps with underscores).

6. **Exceptions**:
   
   - **PEP 8**: Advises using specific exceptions and provides guidelines on exception handling.
   - **Google**: Emphasizes the use of try/except blocks for error handling and provides specific guidelines on exception chaining.

7. **Comments**:
   
   - **PEP 8**: Comments should be complete sentences. Block comments generally consist of one or more paragraphs built out of complete sentences, with each sentence ending in a period.
   - **Google**: Comments should be complete sentences. In-line comments should be separated by at least two spaces from the statement and start with a capital letter. Block comments generally consist of one or more paragraphs built out of complete sentences, with each sentence ending in a period.

### Conclusion

While both PEP 8 and Google's Python Style Guide aim to make Python code more readable and consistent, Google's guide is more prescriptive in certain areas, providing more specific rules and additional guidelines beyond what PEP 8 covers.

## What are the pros and cons of enforcing PEP 484 type hints?

Ensuring strict adherence to PEP 484 by enforcing comprehensive type annotations throughout your code can have significant advantages and some drawbacks. Here’s a detailed look at the pros and cons:

### Pros

1. **Improved Code Quality and Readability**:
   
   - **Documentation**: Type annotations serve as a form of documentation, making it clear what types of inputs a function expects and what it returns. This enhances readability and makes it easier for new developers to understand the code.
   - **Self-Documentation**: Annotations help document the code inline, reducing the need for external documentation.

2. **Early Detection of Errors**:
   
   - **Static Analysis**: Tools like mypy can catch type-related errors before runtime, reducing the likelihood of bugs in production.
   - **Preventing Common Bugs**: Many common bugs, such as those related to incorrect types, can be caught early through static type checking.

3. **Enhanced IDE Support**:
   
   - **Autocompletion**: Modern IDEs can provide better autocompletion and code navigation with type annotations.
   - **Refactoring**: Type information helps IDEs offer more intelligent refactoring tools, improving developer productivity.

4. **Better Maintenance**:
   
   - **Refactoring Safety**: Type annotations make it safer to refactor code by ensuring that changes in function signatures or variable types are consistent throughout the codebase.
   - **Code Reviews**: Type annotations make code reviews more effective by providing clear expectations for function inputs and outputs.

5. **Improved Collaboration**:
   
   - **Team Understanding**: Type annotations make it easier for team members to understand each other’s code, facilitating better collaboration and knowledge transfer.

### Cons

1. **Increased Initial Effort**:
   
   - **Annotation Overhead**: Adding type annotations to an existing codebase can be time-consuming and requires an initial investment in effort.
   - **Learning Curve**: Developers unfamiliar with type annotations or PEP 484 might need time to learn and adapt.

2. **Potential for Overhead**:
   
   - **Complex Types**: For complex types or dynamic code, writing and maintaining type annotations can be cumbersome and may introduce additional complexity.
   - **Verbose Code**: Type annotations can make the code more verbose, potentially reducing readability if not managed well.

3. **Maintenance Burden**:
   
   - **Keeping Annotations Updated**: As the code evolves, type annotations need to be kept in sync with the changes. This can be an additional maintenance burden.
   - **False Positives/Negatives**: Static type checkers are not perfect and might produce false positives or negatives, requiring manual intervention to address.

4. **Performance Considerations**:
   
   - **Development Speed**: Strict type checking can slow down development if developers have to frequently address type-related issues, especially during prototyping or initial development phases.
   - **Dynamic Features**: Python’s dynamic nature can be at odds with static typing, and some dynamic features of Python might be harder to annotate or check.

### Conclusion

Strict adherence to PEP 484 and comprehensive type annotations provide substantial benefits in terms of code quality, error detection, maintenance, and collaboration. However, they also introduce some overhead in terms of initial effort, maintenance, and potential verbosity. Balancing these pros and cons is crucial. For long-term projects, large teams, or critical systems, the benefits often outweigh the downsides. For smaller projects or rapid prototyping, the overhead might be more noticeable, and a more relaxed approach to type annotations could be more appropriate.

## What could a pragmatic approach for running security checks with Bandit look like?

A pragmatic approach to using Bandit for finding common security issues in Python code involves balancing thoroughness with minimizing false positives and maintaining developer productivity. Below is a proposed `bandit.yaml` configuration file that aims to strike this balance.

### Example `bandit.yaml` Configuration

```yaml
# This configuration focuses on the most critical security issues while
# avoiding false positives and unnecessary noise, making it suitable for
# a pragmatic approach in smaller projects or during rapid prototyping.

# List of plugins to run. By default, Bandit runs all the plugins.
# You can specify a subset of plugins if needed.
plugins:
  - blacklist_calls
  - blacklist_imports
  - binding_to_all_interfaces
  - exec_used
  - hardcoded_bind_all_interfaces
  - hardcoded_password_string
  - hardcoded_password_funcarg
  - hardcoded_tmp_directory
  - hashlib_insecure_hash_functions
  - request_with_no_cert_validation
  - sql_statements
  - subprocess_popen_with_shell_equals_true
  - yaml_load

# Exclude certain directories from scanning
exclude_dirs:
  - tests
  - venv
  - .hatch
  - .venv
  - .tox
  - .git
  - __pycache__

# Specify the output format. By default, Bandit uses text format.
output_format: txt

# List of files to exclude from scanning. Use glob patterns.
exclude:
  - tests/*
  - examples/*
  - docs/*

# List of tests to skip (use Bandit test IDs)
skips:
  - B101  # Skip assert statements used
  - B311  # Skip random usage
  - B312  # Skip telnetlib usage
  - B404  # Skip import of insecure hashlib functions

# Custom configuration for individual plugins
plugin_config:
  blacklist_calls:
    bad_name_sets:
      - [eval, exec, execfile, compile]
      - [input, raw_input]
      - [open, file, openfile]
  blacklist_imports:
    bad_import_sets:
      - [telnetlib, ftplib, pickle, cPickle, subprocess, crypt, pwd]
  hardcoded_tmp_directory:
    tmp_dirs:
      - /tmp
      - /var/tmp
      - /dev/shm

# Severity level of issues to be reported (LOW, MEDIUM, HIGH)
severity_level: LOW

# Confidence level of issues to be reported (LOW, MEDIUM, HIGH)
confidence_level: MEDIUM

# Maximum number of lines in a file to be scanned (useful to skip large files)
max_lines: 1000

# Enable recursive scanning
recursive: true

# Verbosity level of the output (0 - minimal, 1 - default, 2 - verbose)
verbosity: 1
```

### Reasoning

1. **Plugins**: Only specific high-impact plugins are enabled to focus on common and significant security issues.
2. **Exclude Directories**: Added common directories that typically do not need security scans, such as `tests`, `venv`, `.hatch`, `.venv`, `.tox`, `.git`, and `__pycache__`.
3. **Exclude Files**: Added glob patterns to exclude certain directories and files such as `tests/*`, `examples/*`, and `docs/*` from scanning.
4. **Skipped Tests**: Some Bandit tests are skipped to reduce false positives and focus on more critical issues:
   - `B101`: Assert statements usage.
   - `B311`: Random usage.
   - `B312`: Telnetlib usage.
   - `B404`: Import of insecure hashlib functions.
5. **Plugin Configuration**: Custom configurations for blacklist calls, imports, and hardcoded temporary directories to target specific high-risk functions and imports.
6. **Severity and Confidence Levels**: Set to report issues with a confidence level of `MEDIUM` or higher and a severity level of `LOW` or higher to balance thoroughness and noise.
7. **Maximum Lines**: Limited the maximum number of lines in a file to be scanned to 1000 to avoid processing extremely large files that might not be relevant.
8. **Recursive Scanning**: Enabled recursive scanning to ensure all relevant files are checked.
9. **Verbosity Level**: Set to a reasonable default (`1`) for meaningful output without being overly verbose.

This configuration ensures that Bandit focuses on the most critical security issues while avoiding false positives and unnecessary noise, making it suitable for a pragmatic approach in smaller projects or during rapid prototyping. Adjust the settings as needed based on your specific requirements and project structure.
