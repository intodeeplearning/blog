---
toc: true
layout: post
description: 
categories: [Markdown]
permalink: /embedding-images-in-google-drive-to-markdown/
search_exclude: false
title: Embedding images in google drive to markdown
show_tags: true
---
## 1. Create a link for your image in your google drive
a. Upload your image to your google drive

b. Right-Click the your file

c. Click on **Get Link**

d. Make sure to change the **Restricted** mode of sharing to **Anyone with the link**


{% include image_box_shadow.html file_id="1L07w0_Qg9q-0Ukm4-K3i8ffyk34FqTzA" alt="get shareable link" %}

e. Click on **Copy Link**. The link will be in the following format:
`https://drive.google.com/file/d/<ID of image>/view?usp=sharing`
   
- \<ID of image\> is your google drive file ID


f. Get the \<ID of image\>  and create a link in the following format for embedding:
`https://drive.google.com/uc?id=<ID of image>`

- This is the link we’ll use in markdown/html code.



For example:
- my link: `https://drive.google.com/file/d/1L07w0_Qg9q-0Ukm4-K3i8ffyk34FqTzA/view?usp=sharing`
- \<ID of image\> is `1L07w0_Qg9q-0Ukm4-K3i8ffyk34FqTzA`
- my embedding link: `https://drive.google.com/uc?id=1L07w0_Qg9q-0Ukm4-K3i8ffyk34FqTzA`



## 2. Use the link in markdown

To embed an image using markdown, use the following:

```markdown
![Example Image](https://drive.google.com/uc?id=1bXzYeegauqB2M6-VZwitEeXHmMiYZIUY)
```
The image will be like:

![sample images](https://drive.google.com/uc?id=1bXzYeegauqB2M6-VZwitEeXHmMiYZIUY)





## 3. (Optional) Use the link in HTML code for more flexibility
Using markdown is easy. However, this does not give us much flexibility in adjusting the images. Instead, we can use the html code below.

```html
<img src="https://drive.google.com/uc?id=1bXzYeegauqB2M6-VZwitEeXHmMiYZIUY"
     alt="sample image"
     style="display: block; margin-right: auto; margin-left: auto; width: 90%;
     box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19)" />
```
I put some shadow for the image and also shrink it to 90%.
The image will be like:

{% include image_box_shadow.html file_id="1bXzYeegauqB2M6-VZwitEeXHmMiYZIUY" alt="sample image" %}