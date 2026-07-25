# JTH Platform — Supplier Management v1.0.0

First admin build for the shared JTH Platform supplier directory.

## Installation

The ZIP is rooted at the website root. Install it using the JTH Patch Installer or extract it so the files land in:

- `/admin/suppliers/`
- `/includes/jth-suppliers.php`
- `/database/jth-suppliers-v1.0.0.sql`

Then open:

`/admin/suppliers/install.php`

Run the installer once. It is safe to run again because it uses additive table creation and `INSERT IGNORE` for defaults.

The Admin tile should link to:

`/admin/suppliers/`

## Included in this build

- Supplier list, search and filters
- Add, edit, activate and deactivate suppliers
- Automatic supplier references such as `SUP-000001`
- Duplicate-name protection
- General, quote, order, accounts and alternative email addresses
- Primary branch and collection information
- Commercial account, payment, delivery and discount information
- Unlimited supplier contacts
- Contact responsibilities for quotes, purchase orders and accounts
- Preferred supplier ranking overall and by material category
- Configurable supplier types, account statuses, contact methods and preference labels
- Configurable supplier capability categories
- In-place AJAX status and preference saving without page jumps
- Audit history for supplier, contact, category and preference changes
- Shared service functions for future Materials, Quoting and Purchasing modules

## Materials category integration

The current Materials catalogue category table was not bundled with this build. Supplier capability categories therefore include an optional `material_category_reference` field. This avoids guessing or overwriting the existing Materials schema. When that schema is formally adopted as the shared category source, the references can be migrated without losing supplier rankings.

## Security and compatibility

- Uses the existing `/includes/auth.php` login/admin protection.
- Uses the existing shared PDO connection where available.
- Falls back to the existing `JTH_DB_*` constants used by current JTH Platform modules.
- Uses CSRF protection for all changes.
- Does not alter the global site version file.
- Does not add the Admin dashboard tile automatically.

## First workflow not included yet

Sending a materials list for supplier pricing, recording returned quotes and applying quoted costs are intentionally left for the next build. This version establishes the supplier data those workflows require.
