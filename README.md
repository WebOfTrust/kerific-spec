# kerific
Browser Extension and Bookmarklet for Concepts, Terminology and Glossaries.

*kerific* is a front plugin or extension that currently only works for Chrome and Brave. It **matches words in any text** on the web that is parseable for kerific **and offers buttons to various glossaries and definitions** in the [SSI](self-sovereign-identity) field.

## Relation with KERISSE
KERISSE is our engine for Concepts and Education targetted at programmers *to be* in the [KERI Suite](keri-suite). All glossaries that [KERISSE](KERISSE) is allowed to scrape are combined in the [Unified Glossary](https://weboftrust.github.io/WOT-terms/docs/glossary-unified?level=2). This unified glossary is based on a large JSON file, which kerific uses to match words in any text and serve the combined glossaries.

## Download kerific
It is in the [Chrome Webstore](https://chromewebstore.google.com/detail/kerific/ckbmkbbmnfbeecfmoiohobcdmopekgmp?hl=nl)

## Specification Template

This is the working area for the Trust over IP specification template.

* [Editor's Copy](https://trustoverip.github.io/specification-template/)

## Using this template

Two ways to use the template:
* The green `Use this template` button in the upper right. Then select `Create new repository` or
* When creating a new repository from the `Repository template` menu select `toip/specification-template`

After setting up your new repository you will need to configure GitHub pages.

Under `Settings -> Code and automation -> Pages` ensure the following settings are applied

* Build and deployment -> Source -> Deploy from a branch
* Build and deployment -> Branch -> gh-pages
* Build and deployment -> Branch -> folder -> / (root)

### Editing locally

In the root of the repository run `npm install` to install dependencies.

Run `npm run render` to render the HTML under `docs/index.html` this can then be previewed in your browser.

Run `npm run edit` to watch for changes and re-render the HTML.

Be sure to remove references to `specification-template` in favor of your new specification!

### Experimental PDF generation

To output a PDF (on macOS, requires Python)

`# brew install pandoc`
`# brew install librsvg homebrew/cask/basictex`

`# python combine.py`
`# chmod +x pdf.sh`
`# ./pdf.sh`

#### Contributing

All Trust Over IP Foundation Technical Stack Working Group contributions are done so under the following licenses:

* [Patent and Copyright Grants](CONTRIBUTING.md)
* [Source Code](SOURCE_CODE.md)

#### Licensing

All Trust Over IP Foundation Technical Stack Working Group deliverables are published under the following licenses:

* [Patent and Copyright Grants](LICENSE.md)
* [Source Code](SOURCE_CODE.md)

#### Getting involved

Join a community of individuals and organizations solving the toughest technical and human-centric problems in digital trust. https://trustoverip.org/get-involved/membership/
