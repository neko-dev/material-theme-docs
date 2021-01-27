# Basic settings

## Language

Edit the **site config** and set `language` to the language you want.

Available languages ​​are:

- العَرَبِيَّة (ar)
- Deutsch (de)
- English (en)
- Español (es)
- Français (fr)
- 日本語 (ja)
- Malay (ms)
- Portuguese (Brazil) (pt-BR)
- 简体中文 (zh-CN)
- 繁體中文 (zh-TW)

> For example, to use Traditional Chinese, the configuration would be:
>
```yaml
language: zh-TW
```

## Site information

### head

Used to configure the generated HTML file header information.

- `favicon`: the favicon
- `high_res_favicon`: the favicon using high quality format
- `apple_touch_icon`: the iOS Home button icon
- `keywords`: the site keywords
- `site_verification`: the verification of search engine console.
  - `google`: Google Search Console
  - `baidu`: Baidu Zhanzhang

> 1. After logged in the console of search engine, choose to use `<meta>` tag to finish the verification. Then console will give you something like:
```html
<meta name="xxxx-site-verification" content="xxxxxxxxxxxxxxxxxxxxxxxxxxxx" />
```
> 2. Simply set `site_verification: xxxx:` with the things like `xxxxxxxxxxxxxxxxxxxxxxxxxxxx`.

- `structured_data`: Default is true. When enable it, the theme will generate the structured-data for SEO. This feature request you configure the **`theme config`** and **`site config`** correctly.So if there are something wrong when `hexo g`, please check your config file or set this value as `false`, then try again.

### url

Used to set jump links.

- `rss`: the rss or atom url.
- `daily_pic`: the redirect url from click on the daily picture
- `logo`: the redirect url from click on the logo

> You can read the [Service](/service/) about how to set up the RSS.
