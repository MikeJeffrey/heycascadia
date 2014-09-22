---
title: Some things I learned about Jekyll and Liquid
layout: post
---

I've been working on a site recently for an open-source project, which is hosted using GitHub pages.

I struggled a fair amound with conditionals, and this is what I learned:

* **Liquid doesn't accept double-quotes for conditionals**. You need to use single quotes.

* **There needs to be a space between the comparison operator and the terms on either side.** You can't run them
  together without a space.

* **You can use any YAML front-matter value, even custom values.** For example, I used `category: docs` for pages
  that are documentation pages. I can access this later with `page.category`.

An example of all of this:

    %7B%25 for page in site.pages %}
      %7B%25 if page.category == 'docs' %}
        ... do something ..
      %7B%25 endif %}
    %7B%25 endfor %}

The above works. What wouldn't work:

    %7B%25 if page.category=='docs' %}...{% endif %} // Need a space before and after operator.
    %7B%25 if page.category == "docs" %}...{% endif %} // Double quotes are not supported; use single quotes.
