## Using Antora 

The Quarkiverse extension template includes skeleton documentation. 
These docs use [Asciidoctor](https://asciidoctor.org/) for content, and [Antora](https://antora.org/) for navigation.
To get started creating your documentation, update the `docs/modules/ROOT/pages/index.adoc` in your project.
If your extension grows more complex and you need multiple pages, add them to `docs/modules/ROOT/nav.adoc`.

## Samples 

Code samples can be put in the `docs/modules/ROOT/examples` folder, and imported into the main documentation with [an `::include` directive](https://docs.asciidoctor.org/asciidoc/latest/directives/include/).
Properties in `docs/templates/includes/attributes.adoc` will be resolved and copied into `docs/modules/ROOT/pages/includes/attributes.adoc` by the Maven resources plugin each build.

## Quarkiverse docs hosting 

Consider adding documentation to the [Quarkiverse docs page](https://docs.quarkiverse.io/). 
The Quarkiverse Hub uses [Antora](https://antora.org/) to aggregate each extension's documentation in the Quarkiverse docs website. 
To register your extension's documentation, open a PR including it in the [antora-playbook.yml](https://github.com/quarkiverse/quarkiverse-docs/blob/main/antora-playbook.yml)

## Migration to Quarkus 3.14

Before 3.14 the config documentation used to be generated in the root directory of your project.
This is not the case anymore.
Therefore, if you upgrade the Quarkus used in your Quarkiverse extention from a version older than 3.14 to any version newer than 3.13 you need to set up the `quarkus-config-doc-maven-plugin` in your project.
A typical diff is described in the [Migration Guide 3.14](https://github.com/quarkusio/quarkus/wiki/Migration-Guide-3.14#publishing-the-config-documentation).