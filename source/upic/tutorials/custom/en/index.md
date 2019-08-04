---
title: uPic tutorial - custom
date: 2019-07-01 21:03:43
toc: true
widgets:
  - type: toc
    position: right
sidebar:
  left:
    sticky: true
  right:
    sticky: true

---

<hr>

<hr><!-- i18n --><div align="right">[**🇨🇳中文**](../) | **🇬🇧English**</div><!-- i18n -->


![custom config](https://gitee.com/gee1k/oss/raw/master/tutorials/custom-host.png)

## 📝 Options instruction

- `API URL`: Background service URL
- `Request method`: The service request mode, support `POST` and `PUT`
- `File field`: The field name of the file object in the upload form
- `Other field`: Request Body。Click the `other field` buttons to configure
- `Request header`: Request Headers。Click the `other field` buttons to configure
- `URL path`: The path to get the image URL in the JSON returned by the upload.[Rule of get URL](#Rule-of-get-URL)
- `Domain`: After uploading, access the URL of the server file.
- `more`: By clicking setting button after `Domain`, you can custom url/folder/patterns to access picture.
  ![custom-host-extension-field](https://gitee.com/gee1k/oss/raw/master/tutorials/custom-host-extension-field.png)

![custom-host-extension](https://gitee.com/gee1k/oss/raw/master/tutorials/custom-host-extension.png)

<hr>

## Rule of get URL

- Example：

```json
{
  "data": "http://xxx.png"
}

# get
["data"]
```

- Example：

```json
{
  "data": {
    "url": "http://xxx.png"
  }
}
# get
["data", "url"]
```

- Example：

```json
{
  "data": {
    "url": [
      "http://xxx.png"
    ]
  }
}

# get
["data", "url", 0]
```

- Example：

```json
{
  "data": [
    {
      "url": "http://xxx.png"
    }
  ]
}

# get
["data", 0, "url"]

```

## 🏷 Dynamic template value

> Both the extended fields and the request headers support the following dynamic templates to get dynamic values

- `{filename}`：Will be dynamically replaced with the file name at the time of upload

## 💌 Our Wechat group

  <small>↓scan the QR code below and join in the group!↓ </small>
	<img src="https://raw.githubusercontent.com/gee1k/oss/master/personal/geee1k.JPG" height="200" style="height:200px">

<hr>
```
