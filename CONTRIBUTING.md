# Contributing

Additions to the project should follow these guidelines for consistency and clarity.

## Structure

The project follows a simple branching structure:

```sh
# Example Structure
. Main Readme
├── topic/
│   ├── topic.md #Main Readme/ToC for topic
│   ├── topic-one.md
│   └── topic-two.md
└── topic/
    ├── topic.md #Main Readme/ToC for topic
    ├── topic-one.md
    └── topic.subtopic/
        ├── topic.subtopic.md #Main Readme/ToC for subtopic
        ├── topic.subtopic-one.md
        └── topic.subtopic-two.md
  ...

# The above translates to:
. README.md
└── core-languages/
    ├── core-languages.md
    ├── css/
    │   ├── css.md
    │   ├── css.core/
    │   ├── css.layout/
    │   ├── css.preprocessors/
    │   └── css.styling-systems/
    ├── html/
    │   ├── html.md
    │   └── html.core/
    ├── javascript/
    │   ├── javascript.md
    │   ├── javascript.frameworks/
    │   └── javascript.core/
    └── markdown/
        └── markdown.md
```

The main idea is to have every topic or sub-topic directory anchored by a README of its own, for general/meta information and for easier navigation as the project scales. Naming conventions should illustrate that structure as shown above.

Each page/topic should be structured as such:

1. Main h1 heading, e.g. "HTML"
2. Navigation links for orientation, e.g., "Home > Core Languages > HTML". The navigation links should be structured as such (note the two linebreaks after the nav [breadcrumbs](https://en.wikipedia.org/wiki/Breadcrumb_navigation)):

    ```sh
    <em>
    <sub><a href='../README.md'>Home</a> > <a href='Link to Parent Topic'>Parent Topic</a> > <a href='#'>Current File/Topic</a></sub>
    </em>
    <br />
    <br />
    ```

3. Content, with links to other sections where appropriate. Should follow [GitHub Markdown](https://guides.github.com/features/mastering-markdown/#GitHub-flavored-markdown) conventions.
