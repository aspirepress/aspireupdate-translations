# AspireUpdate Translations

Translators, everything here is automated tona larhe degree. You only need to translate on the GlotPress site. `.po` files will be extracted from there.  `.mo`, `.json`, and `.l10n.php` files will be generated automatically.

AspireUpdate Translations uses [`Language_Pack_Maker`](https://github.com/afragen/language-pack-maker) installed via `composer` to create a directory of zip archives of the translation files (.mo/.po/.json/.l10n.php) and a `language-pack.json` file containing data to pass to Git Updater or afragen/translations-updater.

The format of the generated JSON file is as follows.

```json
[
  {
    "translations": [
      {
        "type": "(plugin|theme) from Git Updater",
        "slug": "{$slug}",
        "language": "en_US",
        "version": "from Git Updater",
        "updated": "PO-Revision-Date from .po file header",
        "package": "/packages/git-updater-en_US.zip",
        "autoupdate": "1"
      }
    ]
  }
]
```

The update transient expects the `$transient->translations` in the following format.

```php
$transient->translations( array(
	0 => array(
		'type'       => 'plugin',
		'slug'       => 'akismet',
		'language'   => 'de_CH',
		'version'    => '3.1.11',
		'updated'    => '2016-05-12 18:04:38',
		'package'    => 'https://downloads.wordpress.org/translation/plugin/akismet/3.1.11/de_CH.zip',
		'autoupdate' => 1,

	),
) );
```
