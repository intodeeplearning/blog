---
toc: true
layout: post
description: a tutorial about setting up google domain for GitHub Pages
categories: [Github Pages]
permalink: /setup-google-domain-for-github-pages/
search_exclude: false
title: How to setup google domain for your fastpages site (or GitHub Pages)
show_tags: true
hide: 
---
## Introduction

When you publish a site with [GitHub Pages](https://pages.github.com), the default address will look something like this: `https://<username>.github.io/<repo name>`. For example, [https://intodeeplearning.github.io/blog](https://intodeeplearning.github.io/blog).

If you'd like to replace the default address with your custom domain, such as [https://intodeeplearning.com](https://intodeeplearning.com) , follow this tutorial!

### What you will get in this tutorial

- Setting up a custom **www** subdomain, such as **www.example.com**, for your GitHub Pages
- having the apex domain, such as  **example.com**, automatically redirect to **www.example.com**

### What you need

- A GitHub repository ready for publishing, such as [https://github.com/intodeeplearning/blog](https://github.com/intodeeplearning/blog)
- A purchased [google domain](https://domains.google), such as "**intodeeplearning.com**"

<br><br>

## Step 1. Setup in your Github Repo

- Go to Settings > Pages > Custom domain, and add you custom domain name, such as "www.intodeeplearning.com"
    
    {% include image_box_shadow.html file_id="10wHsLyGzueGM2HnZ-5nBYe61afuEq9GX" alt="example image" %}
    

## Step 2. (Optional) You can skip this step if you are NOT using a site generator, such as fastpages, or [Jekyll](https://jekyllrb.com)

If you are using [fastpages](https://fastpages.fast.ai).

- Add a [CNAME file](https://github.com/fastai/fastpages/blob/master/CNAME) in the root of your repo.
    
    ```markdown
    www.intodeeplearning.com
    ```
    
- In [_config.yml](https://github.com/fastai/fastpages/blob/master/_config.yml) set `url` to your custom `www` subdomain and`baseurl` to `""` .
    
    ```bash
    url: 'https://www.intodeeplearning.com'
    baseurl: ''
    ```
    
- In [_action_files/settings.ini](https://github.com/fastai/fastpages/tree/master/_action_files), empty `baseurl`.
    
    ```bash
    baseurl=
    ```
    
- You can also refer to [Fastpages: using a custom domain](https://github.com/fastai/fastpages/blob/master/_fastpages_docs/_setup_pr_template.md#optional-using-a-custom-domain)

## Step 3. Let your custom domain point to your GitHub Pages

- Go to your [google domain registrar](https://domains.google.com/registrar/) and select your domain.

- Go to the **DNS** tab
    
    {% include image_box_shadow.html file_id="1WJldVA2ZBAoUib34drCYYQbyOopxe56h" alt="example image" %}
<br>
    
- Under the **Resource records** section, click **Manage custom records**
    
    {% include image_box_shadow.html file_id="1WN0Uh8owkLyJDHWHEptSzMcuHU8rrzn8" alt="example image" %}
<br>
    
- Create a **CNAME** record that points your **www** subdomain to `<your_github_username>.github.io`

    {% include image_box_shadow.html file_id="1oJGTCf1twGn1fOXoIGbCLaTx2yf5E2en" alt="example image" %}
    
    - Do NOT include the repository name, such as [intodeeplearning.github.io/blog](http://intodeeplearning.github.io/blog). If you include your repository name in the CNAME record to your DNS provider, you’ll get the below message at your GitHub Settings > Pages > Custom domain
        
        {% include image_box_shadow.html file_id="1eqxz86jP8dGRqyPIhNZNh7K915yAw6EY" alt="example image" %}
<br>
        
- Create an **A** record that points to the IP addresses for Github Pages.
    
    {% include image_box_shadow.html file_id="18eTpk2MdrulOCcpSQpbcrYMEG44FwIYZ" alt="example image" %}
    
    - IP addresses in the screenshot
        
        ```markdown
        185.199.108.153
        185.199.109.153
        185.199.110.153
        185.199.111.153
        ```
        
    - Check [here](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#configuring-an-apex-domain) if there's an update in the IP addresses.
<br>

- Open **Terminal** to confirm that your DNS record configured correctly

    - For **CNAME** records, do
        
        ```markdown
        dig www.intodeeplearning.com +nostats +nocomments +nocmd
        ```
        - You should get

            ```bash
            ; <<>> DiG 9.10.6 <<>> www.intodeeplearning.com +nostats +nocomments +nocmd
            ;; global options: +cmd
            ;www.intodeeplearning.com.	IN	A
            www.intodeeplearning.com. 3312	IN	CNAME	intodeeplearning.github.io.
            intodeeplearning.github.io. 3312 IN	A	185.199.110.153
            intodeeplearning.github.io. 3312 IN	A	185.199.111.153
            intodeeplearning.github.io. 3312 IN	A	185.199.109.153
            intodeeplearning.github.io. 3312 IN	A	185.199.108.153
            ```
        
    - For **A** records, do
        
        ```markdown
        dig intodeeplearning.com +noall +answer -t A
        ```
         - You should get

            ```bash
            ;; global options: +cmd
            intodeeplearning.com.	928	IN	A	185.199.109.153
            intodeeplearning.com.	928	IN	A	185.199.108.153
            intodeeplearning.com.	928	IN	A	185.199.110.153
            intodeeplearning.com.	928	IN	A	185.199.111.153
            ```
        

## Step 4. Enable HTTPS for you GitHub Pages

- Go to your github repository settings page, under Settings > Pages, remove your custom domain and save.

- Then add it back and save again.

- Now you should be able to check the **Enforce HTTPS** checkbox
    
    {% include image_box_shadow.html file_id="1z5WlJs0MsnlACouqH5H-dlfnA2jd5sYJ" alt="example image" %}
    

- Note: DNS changes can take **up to 24 hours** to propagate. 

    - You may use [dns propagation checker](https://www.whatsmydns.net/#A/intodeeplearning.com) to check if you DNS has successfully propagated.

    - See [GitHub Pages trouble shoot](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/troubleshooting-custom-domains-and-github-pages) for more questions.

<br><br>
That's it! Your website should be publishing at your custom domain now!

## Reference

- Official Github Tutorial
    - [About custom domains and GitHub Pages](https://docs.github.com/en/enterprise-cloud@latest/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages)
        
        > [We recommend always using a `www` subdomain configurations](https://docs.github.com/en/enterprise-cloud@latest/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages) for your site. If you configure a `www` subdomain, we automatically attempt to secure the associated apex domain.
        > 
        
        > If you configure `www.example.com` as the custom domain for your site, and you have GitHub Pages DNS records set up for the apex and `www` domains, then `example.com` will redirect to `www.example.com`
        > 
        
        > `www`subdomains are the most stable type of custom domain because `www` subdomains are not affected by changes to the IP addresses of GitHub Enterprise Cloud's servers.
        > 
    - [Managing a custom domain for your GitHub Pages site](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#configuring-a-records-with-your-dns-provider)
    - [Configuring a subdomain](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#configuring-a-subdomain)
