---
layout: demo
---
<!-- markdownlint-disable-file first-line-h1 -->

> {{ site.description }}
{: style="font-size: 1.5em" }

For the full guide (usages, etc.), view the project on [GitHub]({{ site.github.repository_url }}).

<!-- markdownlint-disable-next-line blanks-around-headers -->
## Table of Contents
{: .no_toc}

* toc
{:toc}

## What it does

It converts your code blocks tagged with either the `plantuml` or `puml` language into the correspoding PlantUML diagram.

* Markdown

  ````markdown
  ```puml
  Alice -> Bob: Hi there!
  Bob --> Alice: Hello to you too!
  ```
  ````

* Result:

  ```puml
  Alice -> Bob: Hi there!
  Bob --> Alice: Hello to you too!
  ```
