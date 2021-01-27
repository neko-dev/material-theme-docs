# Style Settings

## scheme

Material theme provides a variety of theme designs, also known as "Scheme". Material currently supports two schemes.

### Paradox (default)

This is the original style of Material. The layout is centered and illustrated.

### Isolation

This is a variant of Paradox using Jane style. It is concise and clear.

----

If you want to use one of the themes, delete the '#' before the scheme name.
For example, to select the Paradox scheme, simply use:

```yaml
#scheme: Nexus
scheme: Paradox
#scheme: Isolation
```

## uiux

Used to set the user interface and user experience.

- `slogan`: the slogan displayed in the `blog_info` module, now we support multi line slogan (see below).

Single line slogan:

```yaml
slogan: Slogan
```

Multi line slogan:

```yaml
slogan:
    - "First Line"
    - "Second Line"
    - "Third Line"
```

- `theme_color`: the main color
- `theme_sub_color`: the secondary color
- `hyperlink_color`: the color used for hyperlinks
- `button_color`: the color used for buttons
- `android_chrome_color`: the color of the Chrome address bar
- `buffer`: the top loading progress bar buffers
- `nprogress_color`: the color of the top loading progress bar
- `nprogress_buffer`: the top loading progress bar buffers

> [color palette](https://material.google.com/style/color.html#color-color-palette).

## js_effect

Used to control the JavaScript features.

- `fade`: part of the module to load the page fade effect (default: true)
- `smoothscroll`: page smooth scrolling effects (default: false)

## reading

Used to set the reading experience.

- `entry_excerpt`: the home page outputs the character length of the digest (default: 80)

## thumbnail

Used to set up article thumbnail correlation.

- `purecolor`: the color to fill (solid thumbnail used if no one is set)
- `random_amount`: the number of random pictures taken from the `themes/material/source/img/random` folder

## background

Used to set the site background.

- `purecolor`: the background color
- `bgimg`: the background image path (default: `themes/material/source/img/bg.png`)
- `bing`: used to enable bing pictures
    - `parameter`:
        - `color=`: black, blue, brown, green, multi, orange, pink, purple, red, white, yellow.
        - `type=`: A (animal), C (culture), N (nature), S (space), T (travel).

## img

Used to set the site image.

- `logo`: the logo
- `avatar`: your avatar
- `daily_pic`: the daily picture
- `sidebar_header`: the header picture
- `footerico`: the prefix of the SNS icons from the `themes/material/source/img/footer` folder
- `random_thumbnail`: the path of the random thumbnail
- `footer_image`: you can put as any images as you want at the bottom of `sidebar`.

For instance, you can display the `upyun` logo as following:

```yaml
footer_image:
    upyun_logo:
        link: "https://www.upyun.com/"
        src: "/img/upyun_logo.png"
```

## fonts

- `fonts`: Used to set the site fonts.

> The default values are `Roboto, Helvetica Neue, Helvetica, PingFang SC, Hiragino Sans GB, Microsoft YaHei, Microsoft Yahe, Arial`
> The font settings are more standardized for Material Design, no special requirements without additional changes.
> When update the fonts, you should add fonts embed in `head.yml`. You can read [expert](/en/expert/) about how to use `head.yml`

- `use`: Used to set which fonts lib will be uesd in the theme.

> We have built in three available value of "use": `google` `ustc` `baomitu`. 
> Also, you can configured it as `custom` to use the proxy of google fonts service your like, in order to boost your site in China, where vistors can't load google font normally.
> - `google`: use `fonts.googleapi.com` to load `Roboto` and `Material Icon`.
> - `baomitu`: use `lib.baomitu.com`(a public cdn which maintained by Qihoo 75Team) to load `Roboto`
> - `ustc`: use `fonts.proxy.ustclug.org`(a proxy service of Google Font which maintained by University of Science and Technology of China and USTCLUG) to load `Roboto`
> - `catnet`: use `cdnjs.cat.net`(A super fast public cdn service maintained by Showfom) to load `Roboto` & `Material Icon`
> - `custom`: use the font lib in whose URI your configured in `custom_font_host` to load `Roboto`. It should be a mirror of Google Font.
> **Attention! The URI in `custom_font_host` should with proctol (such as https://) and without `/` at the end**

## card_elevation

Used to set elevation of the card on the list of the posts.
