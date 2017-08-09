---
layout: page
title: Flarum services
permalink: /flarum
---

Hello there !
I'm a regular contributor on the [Flarum Discuss](https://discuss.flarum.org/u/clarkwinkelmann) community forum and member of the [Gravure](https://gravure.io/) ([Flagrow](https://discuss.flarum.org/d/1832-flagrow-nurturing-exquisite-extensions)) extension developer group.

As well as contributing to the community and releasing open-source extensions, I offer some professional services:

(Please note these services are not affiliated with the Flarum, Gravure or Flagrow teams)

## Flarum database migration

As there aren't many Flarum import tools to migrate to Flarum from another platform, I'm launching an experimental service.

Here's the deal: I will migrate your existing forum to Flarum for a fixed price.
See below for the terms.
Here is the pricing:

| | Core | Core + Private messaging |
| --- | --- | --- |
| Standard migration (Core Flarum features only) | Yes | Yes |
| Private message migration (for Flagrow Byobu) | No | Yes |
| Price | 100 CHF / 88 EUR / 103 USD | 150 CHF / 132 EUR / 155 USD |
{: class="plans"}

Please note I might not accept all requests.
As I just started this service, expect changes to these terms in the near future.

### Terms of the Flarum migration service

#### Introduction

This is a *Contract for Work and Services* as defined by [article 363 and following of The Code of Obligations](https://www.admin.ch/opc/en/classified-compilation/19110009/index.html#id-ni16-ni38) of the Swiss law.

This is a data migration service by which the Contractor (Clark Winkelmann, "I") copies data from an existing forum software into a Flarum-compatible format for the Customer ("You").

[Flarum](<http://flarum.org/>) is an open-source software developed by Toby Zerner and Franz Liedke.

[Flagrow Byobu](https://github.com/flagrow/byobu) is an open-source extension for Flarum developed by the [Gravure cooperation](https://gravure.io/).

#### Workflow:

- You send me the name and version of the platform you're currently running
- I validate that's a platform I can import
- You provide me with a backup of your current forum database
- If you use a special configuration with that Forum and it changes the way the data is rendered, provide me with this configuration data as well
- I migrate your data into a Flarum compatible database
- I send you a copy of the new Flarum database
- You install the database and/or Flarum and check everything is working correctly
- Once everything is okay, I'll send you your invoice
- After receiving the payment, I delete all databases copies I have (both your original and your new Flarum one)

Your data will be treated confidently.
No third-party will have access to it and I'll delete it permanently once paid.
I won't use it for any other purpose than the service described here.
I will access random data in your old and new database to check everything went well.

#### The source forum (your previous platform) must meet the following criteria:

- Be open-source
- Be popular
- Use MySQL as database
- Use only core features of the platform (no third-party or optional addons/extensions)

#### Destination forum (Flarum) must meet the following criteria:

- Be a blank forum (or not yet installed)
- Run Flarum beta7 (or higher, once a new release comes out)

I'm not importing data into an existing Flarum with this service.
If you want to merge data from multiple (Flarum or other) forums contact me for a quote.

The database I'll provide you has to be put in-place of the blank Flarum one.

#### Files format

The only file format I accept is an SQL export file (you can create these in phpMyAdmin).
It has to be compatible with MySQL 5.7.

You may compress the file in a `.zip` or `.tar.gz` archive.

I'll send you the Flarum database in a zipped SQL export file as well.

#### What's supported

Flarum (and therefore my "Core" migration service) supports migrating the following data only:

- Users with usernames and bio texts
- Administrative groups (administrator, moderator and other administrative named groups)
- Tags (but not user tags, tags are in fact more like categories)
- Discussions (with title and tags, can be pinned and locked)
- Posts (bbcode and/or markdown content)

Check the Flarum website at <http://flarum.org/> for more info on the software.

The limited Flarum Core features means I won't be able to migrate every single thing from a given other platform.
In particular:

- Only messages formatted in BBCode or markdown will preserve formatting. Messages in HTML or other format will be imported as raw text only
- Private messages or discussions are not supported by Flarum. See below for an option to import them anyway
- Trees of discussions (Reddit or Wordpress-style) will be flattened
- Trees of categories will probably not look exactly the same when migrated to Flarum tags
- User tags can be migrated as Flarum tags (categories) if you want. User tags are not supported in Flarum
- Mentions will only be kept if they use a `@username` syntax
- Only emojis in Unicode or [shortcode](https://emoji.codes/) syntax will be imported
- File/image attachment, polls, karma and other things are not supported by Flarum and therefore won't be imported (see below for options)

I'm also not providing any url redirect tool.
Flarum urls will contain a new id and a slug derivated from the discussion title.
If you want me to setup an url redirect script/extension, contact me for a quote.

#### Private messages

Private messages are not supported in a standard Flarum install.
But if you choose the "Core + Private messaging" option,
I'll import your private messages into tables compatible with the [Flagrow Byobu](https://discuss.flarum.org/d/4762-flagrow-by-bu-well-integrated-advanced-private-discussions) extension.

You will have to install and configure that extension on your forum yourself.
Please read the Flagrow Byobu warnings carefully.
In particular the fact that uninstalling (and in our case, not installing) it will cause all private discussions to become public.

#### Other non-compatible stuff

If your existing forum contains custom extensions with data not compatible with Flarum (Including but not limited to file attachments, polls and user tags),
I can't and won't import it with this service.

However I can create a custom importer to get your data into a third-party Flarum extension of your choice, or even create a Flarum equivalent of your previous feature.
Contact me to get a quote.

#### Delays

After you provide me with the all the necessary data (as highlighted in the Workflow section), I'll get back to you with the migrated database within 10 business days.

After I deliver the migrated database, you have 5 business days to check it and report any issue.

After you validate the work or after the issue checking delay expires, I'll invoice you with a 14 days payment period.

#### Payment

I accept payment via IBAN and [Paypal](https://www.paypal.me/clarkwinkelmann).
You have to take the eventual fees on you, I need to receive the full amount.

Payment can be made in CHF, EUR or USD.
Price is not subject to VAT.

EUR and USD prices are provided for your convenience.
In case of a change in the exchange value of these currencies their value will be updated to reflect the CHF exchange rate.

#### No support

The delivered database is provided as-it without support.
You have to report any defect within the allowed delay.
For the full warranty provisions check the *Contract for Work and Services*.

This contract also does not include support for Flarum or other third-party extensions involved in this service.
Contact the vendor of the software to get support.

#### Let's do it

Ready to migrate your forum or have questions ?
Send me an email at <clark.winkelmann@gmail.com> with details on your current platform.

#### Acceptance of these terms and updates

By sending me your data, you accept these terms in their entirety.

I might change the pricing, the conditions or cancel the service anytime.
Always check this page for the up-to-date description of the service.

For the full history of these terms and services, check the source code of the website on [GitHub](https://github.com/clarkwinkelmann/clarkwinkelmann.com).

`// End of the terms`

---

## Extension development

The extension you desperately need does not exist yet ?
Let's create it.

I usually work for a fixed price based on the the requirements we have to set in advance.
If you want me to improve an existing extension or expect a lot of changes in the near future, I also offer an hourly rate.

Simply email me your requirements to get an estimate.

You want to see some extensions I've worked on ?
Here are a few (some of which were developed with other Flagrow devs):

- [Emoji Picker](https://discuss.flarum.org/d/4787-emoji-picker)
- [Flagrow Bazaar](https://discuss.flarum.org/d/5151-flagrow-bazaar-the-extension-marketplace)
- [Flagrow Fonts](https://discuss.flarum.org/d/6207-flagrow-fonts-easily-add-fonts-to-your-forum)

---

## General help

I often help people free of charge via [Flarum Discuss](https://discuss.flarum.org/) or the [Flagrow Discord](https://discord.gg/ZZ4kbp8) (but no need to mention me, other qualified people will help you there as well),
but if you need custom help I'd be happy to install/fix your Flarum/extension at a hourly rate.
Contact me for details.
