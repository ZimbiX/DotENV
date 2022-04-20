# DotENV
SublimeText Syntax Highlighting support for Environment (.env) Files

## Deprecated

I started using this package to avoid the SublieLinter-shellcheck package complaining about my `.env` files, and I made some improvements to make it more similar to the Bash syntax highlighting. I've since worked out how to avoid the shellcheck conflict and keep using the Bash syntax highlighting instead of needing this package:

- Configure ApplySyntax (Preferences -> Package Settings -> ApplySyntax -> Settings) with:

    ```json
    {
      // ...

      "syntaxes": [
        {
          "syntax": "ShellScript/Bash",
          "rules": [
            { "file_path": ".*/\\.env(\\..+)*$" }
          ]
        }
      ]
    }
    ```

- Configure SublimeLinter (Preferences -> Package Settings -> SublimeLinter -> Settings) with:

    ```json
    {
      // ...

      "linters": {
        "shellcheck": {
          "excludes": [
            "*/.env",
            "*/.env.*",
          ]
        }
      }
    }
    ```

### Links
*[PackageControl.io](https://packagecontrol.io/packages/DotENV)*

### Installation:

#### Package Control:

1. Make sure you already have Package Control installed.
2. Choose Install Package from the Command Palette (`Ctrl+Shift+P` on Windows/Linux Or `⇧⌘P` on OS X)
3. Select `DotENV` and hit **`Enter`**

#### Manually:

1. Clone the repo to your Packages folder.
2. Activate by `Ctrl+Shift+P` and fuzzy search `syntax dotenv` and hit **`Enter`**

#### Preview:

![Comparison](comparison.png)
