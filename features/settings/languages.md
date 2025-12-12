# Languages

Manage languages and translations for your application.

## Overview

The Languages feature allows you to add multiple languages to your application and translate content using the built-in translation tool.

[image_languages_list]

## Accessing Languages

Navigate to **Languages** in the admin panel.

## Language List

The language list displays:
- Language code (e.g., `en`, `vi`, `ja`)
- Actions (Edit, Delete)

## Adding a Language

Fill in language details:
   - **Name** - Language name (e.g., Vietnamese)

## Setting Default Language

Click on star icon in language row

[image_language_default]

## Translation Tool

The built-in translation tool helps you translate strings in your application.

## Steps to Translate

1. Load Default Texts 
2. Translate
3. Build language file

### 1. Load Default Texts

[image_translation_load_default_texts]

### 2. Translate

Click **Translate** button on a language

[image_translation_translate]

### Translation Interface

[image_translation_interface]

| Column | Description |
|--------|---------|
| **Key** | Original text or translation key |
| **Translation** | Translated text |
| **Status** | Translated or Pending |

### Translating Strings

1. Find the string to translate
2. Enter translation in the text field
3. Click **Save** or press Enter
4. Translation is saved immediately

### Filtering Translations

Filter translations by:
- **All** - Show all strings
- **Translated** - Only translated strings
- **Untranslated** - Strings needing translation

### Search

Use the search box to find specific strings by:
- Original text
- Translation key
- Translated text

## How Translations Work

1. Code uses `__('Original Text')` helper
2. System looks for translation in current language
3. If found, displays translated text
4. If not found, displays original text

## Translation Files

Translations are stored in:
- Database for dynamic management
- Can be exported to JSON files

## Best Practices

1. **Translate all user-facing text** - Buttons, labels, messages
2. **Keep translations consistent** - Use same terms throughout
3. **Test translations** - Switch languages to verify
4. **Update regularly** - New features add new strings


---

Previous: [User Settings](user.md)
