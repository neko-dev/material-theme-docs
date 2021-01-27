# Intergrated Service

"Material" has built in lots of Integrated Services. You can set up it easily.

## RSS

First, you should install the plugin [hexo-generator-feed](https://github.com/hexojs/hexo-generator-feed). Read the plugin's `README.md` to install and configure it.

Then configure `theme config`  [url: rss](/en/intro/#url) with the URI.

## topPost

Use this to pin post at the top of the list of posts.
If you want to use this WIP feature, please install `hexo-helper-post-top` :

```bash
npm install hexo-helper-post-top --save
```

Now you can use `front-matter` `top: true` to pin your posts what you want to.

----

You can configure third-party services by navigating to `Integrated Services` in the **theme config**

## Comment system

Used to set up a comment system.

See [comment system](/en/services/#Comment-system) for more information.

- `use`: `disqus` `disqus_click` `changyan` `livere` `valine` or `gitalk`

> When Using `disqus_click`, post won't load Disqus automatically. The pages will load Disqus when the vistors click the button. This feature will help to improve some people's browse exprience from where they can't load Disqus normally, such as China.

> The livere built in the Material is `city_verison`.

> [Document for Gitment Comment System](https://github.com/imsun/gitment/blob/master/README.md)
> [Document for Valine Comment System](https://github.com/xCss/Valine/blob/master/README.md)
> [Document for Gitalk Comment System](https://github.com/gitalk/gitalk/blob/master/readme.md)

- `shortname`: the shortname of duoshuo and disqus
- `changyan_appid`: the APPID of changyan
- `changyan_conf`: the CONF of changyan
- `changyan_thread_key_type`: path #identifier of posts. `path` as default.
- `livere_data_uid`: You can find the `datd_uid` from the provided code.
- `gitment_repo`: git repo of the gitment
- `gitment_owner`: git repo's owner of the gitment
- `gitment_client_id`: github app client id
- `gitment_client_secret` : github app client secret 
- `valine_leancloud_appId`: leancloud application app id
- `valine_leancloud_appKey`: leancloud application app key
- `valine_notify`：true | false Enable mail notify or not. Read the [wiki](https://github.com/xCss/Valine/wiki/Valine-%E8%AF%84%E8%AE%BA%E7%B3%BB%E7%BB%9F%E4%B8%AD%E7%9A%84%E9%82%AE%E4%BB%B6%E6%8F%90%E9%86%92%E8%AE%BE%E7%BD%AE) for details.
- `valine_placeholder`: What text to show when there are no comments.
- `gitalk_repo` git repo of the gitalk
- `gitalk_owner`: git repo's owner of the gitalk
- `gitalk_client_id`: github app client id
- `gitalk_client_secret` : github app client secret 

## Search system

### Google

Call the Google search engine to search your site.

```yaml
search:
    use: google
```

### Local Search

The [hexo-generator-search](https://github.com/PaicHyperionDev/hexo-generator-search) plugin needs to be installed when using local search.

```yaml
search:
    use: local
```

### Swiftype

Sign up for [Swiftype](https://swiftype.com/). In your Swiftype installation code, you'll find a line like `_st ( 'install', 'myKey', '2.0.0');`.

```yaml
search:
    use: swiftype
    swiftype_key: myKey
```

## Browse statistics

### Site Analytics

Material theme has a built in Baidu's, Google's website analytics and CNZZ's analytics service.You can easily set the ID to enable it.

- `use`: Set which analytics you want to use.  Available values are baidu | google | cnzz
- `xxxx_site_id`: the site_id that analytics service provide.

> - Google will give the `site ID` with `UA-` begin; 
> - Baidu will give your a JavaScript URI like `hm.js?xxxxxxxxx` and `xxxxxxxx` is the site_id that you need.
> - in CNZZ's code, there will be `z_stat.php?id=xxxxxxxxxxxx` and `&web_id=xxxxxxxxxxx`. Both of these `xxxxxxxxxx` should be the same. And this `xxxxxxxxx` is the site_id of cnzz.

### Other Analytics

You should left the all the site_id empty below. Then you can add the analytics code in `head.yml`. You can read the [expert](/en/expert/) about how to use `head.yml`.

### Leancloud

Open the LeanCloud website and go to the [registration page](https://leancloud.cn/login.html#/signup) to register. After the mailbox is activated, click on the avatar to access the console page

Create a new application (the default type is JavaScript SDK), click Apply to enter;

Create a Class named `Counter`
Note: `ACL Permissions` must be `unrestricted`

You can find `app_id` and `app_key` in `application -> Settings -> Application Key`.

```yaml
leancloud:
    enable: true
    app_id: #app_id
    app_key: #app_key
    av_core_mini: "https://cdn1.lncld.net/static/js/av-core-mini-0.6.1.js"
```

> Add your blog domain to `application -> Settings -> Security Center` to ensure data security calls.

#### Busuanzi

To use the view statistics, simply set:

```yaml
busuanzi:
    enable: true
    all_site_uv: false
    post_pv: false
    busuanzi_pure_mini_js: "https://dn-lbstatics.qbox.me/busuanzi/2.3/busuanzi.pure.mini.js"
```

Parameters are:

- `all_site_uv`: counts the number of unique visitors to the site
- `post_pv`: the number of page views for each post
- `busuanzi_pure_mini_js`: You can save the js to your webserver or CDN, then set the URI here.
