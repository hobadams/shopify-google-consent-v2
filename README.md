# Google Consent V2 for Shopify

## Description

This adds a banner at the bottom of your website asking for consent and sends the answer to your `gtag` to be used by Google Ads / Tag manager / Analytics.

## How to use

The assumption is you already have `gtag` code setup in your `layout/theme.liquid` file.

### 1. Setup defaults

push default `consent` values to your tag...

```html
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag() {
    dataLayer.push(arguments);
  }
  gtag("js", new Date());

  gtag("config", "[YOUR-TAG]");

  // Add this code
  gtag("consent", "default", {
    ad_storage: "denied",
    analytics_storage: "denied",
    ad_user_data: "denied",
    ad_personalization: "denied",
  });
</script>
```

### 2. Add the following snippet

Add the file `snippets/google-consent.liquid` to your theme.

The code for this can be found [here](./snippets/google-consent.liquid)

### 3. Add the snippet to your theme file

In `layout/theme.liquid` add the following code **inside** the body tags near the bottom

```liquid
{% render 'google-consent' %}
```

### 4. TEST

Please test everything works as expected!!
