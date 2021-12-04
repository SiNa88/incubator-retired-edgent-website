<!--
{% comment %}
Licensed to the Apache Software Foundation (ASF) under one or more
contributor license agreements.  See the NOTICE file distributed with
this work for additional information regarding copyright ownership.
The ASF licenses this file to you under the Apache License, Version 2.0
(the "License"); you may not use this file except in compliance with
the License.  You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
{% endcomment %}
-->

# Apache Edgent website

## Location

http://edgent.incubator.apache.org/

## How it works

This procedure was borrowed in part from the [Apache Apex site](https://git-wip-us.apache.org/repos/asf?p=incubator-apex-site.git) except we use Jekyll.

The `master` branch of this repo contains the source files that are used to generate the HTML that ultimately gets pushed to the incubator site. The `asf-site` branch is where the actual generated files are stored. Note that this branch must contain exactly one folder called `content`, and so has been checked out as an orphan branch with its own commit history apart from the `master` branch. See the *Contributing* section below.

Through a [gitpubsub](http://www.apache.org/dev/gitpubsub.html) mechanism on the apache.org server, files are taken from the `asf-site` branch and pushed to the live server.

## Contributing

If you would like to make a change to the site:

1. Fork the [GitHub mirror](https://github.com/apache/incubator-edgent-website)
2. Create a new branch from `master`
3. Add commit(s) to your branch
4. Test your changes locally (see the *Developing* section)
5. Open a pull request in the GitHub mirror
6. A committer will merge your changes if all is good

If you are a committer, do the following:

1. Update the master branch with your (or a Pull Request's) change
2. Push updated master to the [ASF remote master](https://git-wip-us.apache.org/repos/asf/incubator-edgent-website.git)
3. Run `build.sh` from the master branch directory (requires Jekyll). This checks out and updates the `asf-site` branch with a new commit of the build from the current branch.
4. At this point, you should be on the `asf-site` branch. Simply push this branch to the asf remote with `git push origin asf-site` and the site will automatically be updated within seconds.

Note: If you want to try out the website locally on the asf-site branch before you push, you can do so with `jekyll serve -d content --skip-initial-build` and point your browser to `http://localhost:4000`.

### Style Guide

The website utilizes [Markdown](http://daringfireball.net/projects/markdown/) as the basis for website content. This [cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) may prove useful.

In order to ensure a consistent user experience, these guidelines should be followed:

1. For all headers, use sentence-style capitalization
   * Capitalize the first word of the title/header or subtitle/subheader
   * Capitalize any proper nouns and certain other types of words (e.g., programming terms)
   * Use lowercase letters for everything else
2. Page headers should start at Level 2 using `##` in order to have them be automatically added to the Table of Contents
3. Do not skip header levels. For instance, do not jump from `##` to `####`.
4. Use section headings as a way to separate large blocks of content and as reference markers in the Table of Contents
5. Code references (e.g., to a Java class) should be placed in [inline code blocks](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#code) using a single backtick `` ` ``
6. For [code blocks](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#code), use three backticks `` ``` ``, and if applicable, specify the language for syntax highlighting
7. Avoid using raw HTML tags. Use the equivalent Markdown syntax.
8. Whitespaces
   * Use one whitespace between sentences.
   * Use one blank line between paragraphs for the best readability
   * Do not use leading whitespace, except for special cases, such as indenting within list items
   * Do not use trailing whitespace, except for the case where a line break is needed. In that case, end a line with two spaces.
9. Use correct spelling and grammar, especially for references to other projects. For example, use *GitHub*, not *Github*.

## Developing

1. Make your changes under the `site` directory: `cd site`
2. `jekyll serve`
3. Point your browser to `http://localhost:4000`

