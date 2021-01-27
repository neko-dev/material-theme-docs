## Installing "Material"

Installation of an Hexo theme is quite simple. You simply need to put the theme directory inside the `themes` directory of your site and modify the theme config.

You can get a [stable release](https://github.com/viosey/hexo-theme-material/releases) from Github in a timely manner.

## Enable "Material"

Download a [stable release](https://github.com/viosey/hexo-theme-material/releases) and extract the content inside the `themes/material` directory.
Once you have the `themes/material` folder, open the **site config**, find the `theme` field, and change its value to `material`.

> The folder `themes/material` can be named differently if you wish. You simply have to adapt the `theme` field accordingly.

**The `_config.yml` file does not exist in the theme, you need to manually duplicate the `_config.template.yml` file and rename it to `_config.yml`**

Run `hexo s --debug` and go to [`http://localhost:4000`](http://localhost:4000) to make sure the site is running properly.

## Update "Material"

Save your `_config.yml` file somewhere. Then download a new [stable release](https://github.com/viosey/hexo-theme-material/releases) and extract the content inside the `themes/material` directory. Finally reconcile the new version of the `_config.yml` with the one you saved.

The previous commands will put aside your custom config, pull the update reapply your modifications. Fix conflicts if needed.
