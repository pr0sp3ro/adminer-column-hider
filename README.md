# Adminer Column Hider

Hide columns you do not need while browsing a table in Adminer 6.1.2. Bring them back at any time from the **Columns** menu above the results.

## Features

- Toggle entire columns, including their headers and values.
- Restore every column with **Show all**.
- Remember hidden columns across page reloads, sorting and pagination.
- Keep separate preferences for each Adminer installation path, connection, user, database, schema and table.
- Keep record selection and editing controls available.

No dependencies are required beyond Adminer 6.1.2 and a modern browser with JavaScript enabled.

## Installation

Copy `column-hider.php` into your Adminer installation's `adminer-plugins/` directory. Copy `assets/column-hider.js` and `assets/column-hider.css` into `adminer-plugins/assets/`.

Add the plugin to the array returned by `adminer-plugins.php`:

```php
new Adminer\AdminerColumnHider(),
```

Adminer automatically loads PHP files from `adminer-plugins/`. If you store assets elsewhere, pass their public URL path to the constructor:

```php
new Adminer\AdminerColumnHider(assetsPath: 'plugins/assets'),
```

Disable other column-hiding plugins to avoid conflicting visibility controls.

## Usage

Open a table's records and expand **Columns** above the results. Uncheck a column to hide it. Check it again to restore it, or choose **Show all** to restore every column.

Column preferences are stored locally in your browser. They are not synchronized between browsers or devices. If browser storage is unavailable, toggles still work until the page is reloaded.

The menu appears when a table has result columns. It does not affect custom SQL results or table structure screens.

## Privacy

Hiding a column only changes its display. Its data still reaches the browser and remains in the page. This plugin is a viewing convenience, not an access-control mechanism, and does not change queries or exports.
