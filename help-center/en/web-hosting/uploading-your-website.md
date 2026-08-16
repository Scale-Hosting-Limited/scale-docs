---
title: Uploading your website
slug: uploading-your-website
description: Get your site files onto the server with the file manager or SFTP.
---

There are two easy ways to upload your website.

## Option 1: the file manager

1. Open your web hosting service and click **File Manager**.
2. Navigate to your web root — usually `public_html` (or `htdocs`).
3. Upload your files there. If you have a `.zip`, upload it and extract in place.

Your homepage should be named `index.html` or `index.php` so it loads first.

## Option 2: SFTP

For larger sites, use an SFTP client such as FileZilla:

1. Copy the **host, port, username and password** from your service page.
2. Connect, open the web root, and drag your files across.

## Databases

If your site needs a database (for example WordPress), create one from the
control panel's **Databases** section, then use the database name, user and
password in your app's configuration.

## Go live

Once files are in the web root and your domain points at the server, visit your
domain to check it loads. If you see a default page, make sure your `index` file
is in the web root.
