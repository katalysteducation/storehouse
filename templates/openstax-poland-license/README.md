# Software license for projects by OpenStax Poland

## Applying the license

1.  Copy `LICENSE.template` to the root directory of a project as `LICENSE`.

2.  Edit it and change `CURRENT YEAR` in the copyright notice to current 
    year (e.g. 2018).

3.  Include the following notice at the beginning of each source file
  
    ```
    Copyright CURRENT YEAR OpenStax Poland
    Licensed under the MIT license. See LICENSE file in the project root for
    full license text.
    ```

    Again, changing `CURRENT YEAR` to current year.

4.  Include appropriate license information in a packaging system used by 
    the project:

    - For [npm](npmjs.com): in `package.json` add `"license": "MIT"`.
    - For [Rust Cargo](crates.io): in `Cargo.toml` add `license = "MIT"` to
      the `[package]` section.
    - For Python: add `license="MIT"` as a keyword argument to invocation
      of the `setup()` function in `setup.py`
