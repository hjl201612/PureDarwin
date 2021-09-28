# PureDarwin Coding Style

This document is a work in progress. If you are editing anything that does not conform
to the below standards, please follow the formatting that is already used for the time being.
An editorconfig file is provided to help contributors to adhere to these rules.

## All files

* No trailing whitespace, including on blank lines. If trimming trailing whitespace from a file, always commit the whitespace changes separately from the functional changes for ease of review.
* Should always end with one (and only one) newline. No blank lines at the end of a file.

## CMake

* Four-space indent; the editorconfig file should help enforce this.
* Use single blank lines where appropriate to aid readability.
* `add_subdirectory()` calls in CMakeLists.txt files should be sorted alphabetically, with uppercase letters coming before lowercase letters.
* Always name targets after the name of their output binary. If you are building a Darwin component trarget, do include “lib” if it is present in the output filename; CMake will detect this and set the `PREFIX` property accordingly to prevent “lib” appearing twice in the filename. This will _not_ automatically occur for host tool targets, so omit “lib” from target names there.
* When adding compiler definitions, keep them alphabetized unless it breaks something.
* Try to keep include directories alphabetized in the CMakeLists file, but there are places where doing so will break the build.
* Separate build rules for separate binaries with three blank lines. Put `install()` and `add_subdirectory()` calls together in their own section at the end of the file, separated by three blank lines from the others.
* Look in the source files in the scripts/cmake folder for documentation about what each function or macro does.