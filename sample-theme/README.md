# Readme

The only required thing is the `content` folder. Each language/platform has its own naming conventions
so you're free to install packages and do whatever else in the project folder.

The following scheme renders a layout idea:

```
content/               -- all your tutorials for the same theme
  1.first-tutorial/    -- tutorial folder
    assets/            -- asset files
    challenges/
      1.1.{code}.md    -- challenge #1 file
      1.2.{code}.md    -- challenge #2 file
      2.1.{code}.md    -- challenge #3 file
      2.2.{code}.md
      2.3.{code}.md
  2.second-tutorial/
    assets/
    challenges/
ignore/                -- stuff you want to (git-)ignore
node_modules/          -- NPM dependencies (language-spefic)
.gitignore
package.json           -- project specification (language-spefic)
```

Please also check our sample [content](./content).

*Current theme/tutorial structure represents an initial idea that each author will curate a single theme.
That will likely change so tutorials will probably get themeID reference (in YAML) and will probably
lose initial number (in folder name). It will be trivial to update and no bigger structural changes
are planned so far ;)*
