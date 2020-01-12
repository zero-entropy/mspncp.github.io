---
layout: default
title: Home
nav_order: 1
description: "The OpenSSL Project Pages"
permalink: /
---

# OpenSSL Project Pages

This site here is focused on the OpenSSL development process on GitHub.
If you are looking for the official OpenSSL website, please visit
[www.openssl.org](https://www.openssl.org).

_Note: this site is under construction and does not represent an official OpenSSL site yet._

## About the project

OpenSSL Project Pages is &copy; 2019 by the [OpenSSL Software Foundation](https://www.openssl.org).

### License

The content of this site is licensed under the [Apache License 2.0](/LICENSE/).

### Contributing

When contributing to this repository, please first discuss the change you wish to make via issue,
email, or any other method with the owners of this repository before making a change. Read more about becoming a contributor in our GitHub repo [TBD]

#### Thank you to all contributors of the OpenSSL Project Pages!

<ul class="list-style-none">
{% for contributor in site.github.contributors %}
  <li class="d-inline-block mr-1">
     <a href="{{ contributor.html_url }}"><img src="{{ contributor.avatar_url }}" width="32" height="32" alt="{{ contributor.login }}"/></a>
  </li>
{% endfor %}
</ul>

### Code of Conduct

TBD
