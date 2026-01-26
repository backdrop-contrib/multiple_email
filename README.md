# Multiple E-mail Addresses

Add and manage multiple e-mail addresses per user account in Backdrop. Users can register extra addresses, confirm them, pick any confirmed address as primary, and manage them from their profile without exposing the core primary tab.

## Features
- Multiple e-mail addresses per user with one designated primary.
- Optional hiding of the core e-mail field on the profile edit form.
- Per-address confirmation flow with resend support.
- Ability to promote any confirmed address to primary.
- Optional editing and deletion of non-primary addresses.
- Password reset routing to confirmed secondary addresses (configurable).
- Dedicated profile tab for managing addresses: `user/%/edit/email-addresses`.

## Requirements
- Backdrop CMS 1.x

## Installation
1) Install the module using the standard Backdrop process: https://backdropcms.org/guide/modules.
2) Navigate to Administration › Configuration › User accounts › Multiple E-mails (`admin/config/people/multiple-email`) to review settings.
3) Assign permissions as needed (see below).

## Configuration
Key settings include:
- Hide e-mail field on the main profile edit form for users allowed multiple e-mails.
- Allow editing of non-primary addresses.
- Control password reset delivery (disabled, confirmed-only, all addresses).
- Confirmation attempt limits and expiration window.
All settings live at `admin/config/people/multiple-email` with inline help text.

## Usage
- Open a user’s profile and use the Email addresses tab (`user/%/edit/email-addresses`) to add, confirm, resend confirmation, mark primary, edit, or delete addresses.
- Primary address changes happen in this tab; the core profile e-mail field can be hidden to avoid confusion.

## Permissions
- `use multiple emails` — allow users to add/manage their own additional addresses.
- `administer multiple emails` — full administration of settings and any user’s addresses.

## Hooks
- `hook_multiple_email_register($email)` — fires when an address is registered (before confirmation).
- `hook_multiple_email_confirm($email)` — fires when an address is confirmed.
- `hook_multiple_email_delete($eid)` — fires when an address is deleted.

## Issues
Report bugs and feature requests at https://github.com/backdrop-contrib/multiple_email/issues.

## Current Maintainers
- [Alan Mels](https://github.com/alanmels)

## Credits
- Originally written for Drupal by Joshua Benner <joshbenner@gmail.com>.
- Ported to Backdrop CMS by [Alan Mels](https://github.com/alanmels).
- Port sponsored by [AltaGrade](https://www.altagrade.com), a Drupal and Backdrop hosting provider.
