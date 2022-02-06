# docums-print-site-plugin

[Docums](https://khanhduy1407.github.io/docums/) plugin that adds a page to your site combining all pages, allowing your site visitors to *File > Print > Save as PDF* the entire site.

## Installation

Install the plugin using `pip3`:

```bash
pip3 install docums-print-site-plugin
```

Next, add the following lines to your `docums.yml`:

```yaml
plugins:
  - search
  - print-site
```

> :warning: Make sure to put `print-site` to the **bottom** of the plugin list. This is because other plugins might alter your site (like the navigation), and you want these changes included in the print page.

> If you have no `plugins` entry in your config file yet, you'll likely also want to add the `search` plugin. Docums enables it by default if there is no `plugins` entry set.

## Usage

- Navigate to `/print_page/` or `print_page.html`
- Export to standalone HTML (see [export to HTML](how-to/export-HTML.md))
- Export to PDF using your browser using *File > Print > Save as PDF*  (see [export to PDF](how-to/export-PDF.md))
