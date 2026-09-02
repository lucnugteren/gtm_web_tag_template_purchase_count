# Purchase Count Tag Template for GTM

Use this GTM web tag template to keep a first-party purchase count cookie (`__ln_pc`). Every time the tag fires, the count goes up by one, so the cookie reads `1` on a visitor's first purchase and `2` or more on every purchase after that. Use it to tell new customers from returning ones in Google Ads, for example to feed the new customer acquisition goal or to bid differently on both groups.

The cookie is only written when `analytics_storage` consent is granted and lives for one year.

## Installation

1. Download [`template.tpl`](template.tpl).
2. In GTM, go to **Templates**, then **Tag Templates**, then **New**.
3. Open the menu in the top right, click **Import**, and select `template.tpl`.
4. Click **Save**.
5. Create a new tag of type **Purchase Count** and fire it on your `purchase` event.
6. Under **Advanced Settings**, then **Tag Sequencing**, set it to fire **before** your Google Ads conversion tag, so the conversion tag reads the updated count.

## Reading the value

Create a **1st Party Cookie** variable named `__ln_pc`. A value of `1` means a new customer, anything higher means a returning customer. Map that to the `new_customer` parameter of your Google Ads conversion tag, or send it as a custom dimension to GA4.

## Settings

The template has no fields. Cookie name, one-year lifetime and `SameSite=Lax` are fixed in the code.

## Companion templates

- [Shopify Custom Pixel](https://github.com/lucnugteren/shopify_custom_pixel) for a GTM dataLayer in Shopify checkout.
- [User ID tag template](https://github.com/lucnugteren/gtm_web_tag_template_user_id) for external ID matching in Meta.
- [Restore GCLID tag template](https://github.com/lucnugteren/gtm_web_tag_template_restore_gclid) for Safari-stripped click IDs.

More at [lucnugteren.com/resources](https://lucnugteren.com/resources).
