# Adding a print button

You might want to customize your site to include a 'print' button on every page that will lead to the print page. See the example in the top right corner of this page 👆.

Docums supports [theme extension](https://khanhduy1407.github.io/docums/user-guide/styling-your-docs/#using-the-theme-custom_dir), an easy way to override parts of a theme. That will allow you to add a button to the top of every page.

This plugin adds to the context a `page.url_to_print_page` which contains the relative link from a page to the print page. You can use `page.url_to_print_page` when customizing a theme:

## Adding a print button to docurial theme

In the [docurial](https://khanhduy1407.github.io/docurial) theme you can create an override for `main.html` (see [customization](https://khanhduy1407.github.io/docurial/customization/#overriding-template-blocks)).

_Example_:

=== "docums.yml"

    ```yaml
    theme:
    name: material
    custom_dir: docs/overrides

    plugins:
        - print-site
    ```

=== "docs/overrides/main.html"

    ```jinja
    {% extends "base.html" %}

    {% block content %}
    
    {% if page.url_to_print_page %}
        <a href="{{ page.url_to_print_page }}" title="Print Site" class="md-content__button md-icon">
            {% include ".icons/material/printer.svg" %}
        </a>
    {% endif %}

    {{ super() }}
    {% endblock content %}
    ```


## Adding a print button to docums theme

You can also [customize](https://khanhduy1407.github.io/docums/user-guide/custom-themes/#creating-a-custom-theme) the base docums theme, by overriding `main.html`.

_Example_:

=== "docums.yml"

    ```yaml
    theme:
        name: docums
        custom_dir: docs/overrides

    plugins:
        - print-site
    ```

=== "docs/overrides/main.html"

    ```jinja
    {% extends "base.html" %}

    {% block repo %}
        {% if page.url_to_print_page %}
            <li class="nav-item">
                <a href="{{ page.url_to_print_page }}" title="Print Site" class="nav-link">
                    <i class="fa fa-print"></i> Print
                </a>
            </li>
        {% endif %}

    {{ super() }}
    {% endblock repo %}
    ```
