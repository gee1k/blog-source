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


![custom config](https://qiniu.svend.cc/tutorials/custom-host.png)

## 📝 Options instruction

- `API URL`: Background service URL
- `Request method`: The service request mode, support `POST` and `PUT`
- `File field`: The field name of the file object in the upload form
- `Other field`: Request Body。Click the `other field` buttons to configure
- `Request header`: Request Headers。Click the `other field` buttons to configure
- `URL path`: The path to get the image URL in the JSON returned by the upload.[Rule of get URL](#Rule-of-get-URL)
- `Domain`: After uploading, access the URL of the server file.
- `Save Key`: The path to file storage (including folders). `Supports {year} {month} {day} {hour} {minute} {second} {since_second} {since_millisecond} {random} {filename} {.suffix} and etc. For example, the uploaded file is uPic.jpg, set to \"uPic/{filename}{.suffix}\", it will be saved as: uPic/uPic.jpg.`
- `The after Save Key input is Suffix`: This will be used for custom picture processor. 
  ![custom-host-extension-field](https://qiniu.svend.cc/tutorials/custom-host-extension-field.png)

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
```
