# Contributing

You can contribute to the wiki by:

- Updating the content
- Translating the wiki into another language

---

## Updating the Content

When updating content, follow these guidelines:

- **Clarity and Conciseness**: Ensure your changes are clear and easy to understand.
- **Formatting**: The wiki uses [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/). Read their docs to see what kind of formatting features you can use on the site.
- **Language**: The default language is English. If you add information in another language, you must also include the same information in English.

### Testing Changes

You can test changes by forking the repo and downloading to your local machine. Then run:

```bash
pip install mkdocs-static-i18n[material]
mkdocs serve
```

---

## Translating the Wiki

To translate the wiki into a new language, follow these steps. Always base your translation on the English text, as English is the default language.

These instructions use translating to Spanish as an example.

### 1. Update `mkdocs.yml`

Add your language under the `languages` section in the `mkdocs.yml` file using the following format:

```yaml
- locale: es
  name: 🇪🇸 Español
```

#### **Required Fields**

- Replace `locale` with a valid [ISO-639-1](https://en.wikipedia.org/wiki/ISO_639-1) two-letter language code (e.g., `en`) or a [five-letter language code](https://www.mkdocs.org/user-guide/localizing-your-theme/#supported-locales) with territory/region (e.g., `en_US`).
- Replace `name` with the name of the language in its native form. Precede the name with the country emoji (e.g., `🇪🇸 Español`).

#### **Optional Fields**

These fields are not mandatory but are recommended if possible:

- `site_name`: Specify the name of the site in your language.
- `site_description`: Provide a brief description of the site in your language.
- `nav_translations`: Translate navigation menu items.
- `translations`: Other items to translate

##### Example of `nav_translations`

If the `nav` section in `mkdocs.yml` looks like this:

```yaml
nav:
  - Home: index.md
  - UI Overview: ui_overview.md
```

You can translate it as follows:

```yaml
nav_translations:
  Home: Hogar
  UI Overview: Descripción general de la interfaz de usuario
```

##### Example of `translations`

Some additional strings in `mkdocs.yml` under the `extra` section require translation. These look like this:

```yaml
extra:
  translations:
    obtainium_website: Obtainium Website
    made_with: Made with
```

You can translate it as follows:

```yaml
extra:
  translations:
    obtainium_website: Sitio web de Obtainium
    made_with: Hecho con
```

---

### 2. Translate `.md` Files/Images

The `.md` files contain the main content of the wiki. To translate:

- Copy a file, such as `index.en.md`.
- Rename it, replacing `en` with your language code (e.g., `index.es.md`).
- Replace the English text with your translation while staying as close to the original as possible.

If images need to be translated, this is done in the same way.

#### Translating Admonitions

When translating admonitions (e.g., `!!! info` blocks):

- **Do not translate** the admonition type (e.g., `info`). Only translate the text within quotation marks and the body content.

Example:

```markdown
!!! info "What is Obtainium?"
    An app.
```

would become 

```markdown
!!! info "¿Qué es el Obtenido?"
    Una aplicación.
```

For admonitions without quotation marks, add translations in `mkdocs.yml` under your language section:

```yaml
admonition_translations:
  info: Información
```

---

That's it! Now you can open a pull request to get your changes merged!
