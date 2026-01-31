# 🎬 Ginisisila Cartoon API

> A simple API to search, browse, and fetch cartoon episodes from Ginisisila & Lakvision TV.
> Built by **Kawdhitha Nirmal** | `CodeXSL Developer`

---

## 🌟 Base URL

```
https://ginisisila.netlify.app/
```

All endpoints are prefixed with `/api`.

---

## 📚 Endpoints

### 1️⃣ Search Cartoons

Search for cartoons by name.

**Endpoint:**

```
GET /api/search?name=<cartoon_name>&i=<page_number>
```

**Query Parameters:**

| Parameter | Description                | Default |
| --------- | -------------------------- | ------- |
| name      | Cartoon name to search     | -       |
| i         | Page number for pagination | 1       |

**Example Request:**

```bash
GET https://ginisisila.netlify.app/api/search?name=ruby
```

**Example Response:**

```json
{
  "page": 1,
  "results": [
    {
      "title": "Ruby and the Well 60",
      "link": "https://ginisisilacartoon.net/watch.php?id=243093",
      "thumbnail": "https://lakvisiontv.net/thumb.jpg",
      "channel": "Lakvision TV",
      "channelLink": "https://lakvisiontv.net",
      "views": 1234
    }
  ]
}
```

---

### 2️⃣ Get Episode Info

Fetch details for a specific episode.

**Endpoint:**

```
GET /api/episode?url=<episode_url>
```

**Example Request:**

```bash
GET https://ginisisila.netlify.app/api/episode?url=https://ginisisilacartoon.net/watch.php?id=243093
```

**Example Response:**

```json
{
  "title": "Ruby and the Well 60",
  "embed": "https://lakvisiontv.net/embed.php?id=243093&autoplay=0",
  "url": "https://bysezoxexe.com/e/ohbcoeb7m57l"
}
```

> ⚠️ YouTube embeds are converted to **[https://youtu.be/VIDEO_ID](https://youtu.be/VIDEO_ID)** format automatically.

---

### 3️⃣ Get All Channels

List all channels available.

**Endpoint:**

```
GET /api/channel
```

**Example Request:**

```bash
GET https://ginisisila.netlify.app/api/channel
```

**Example Response:**

```json
[
  { "id": 1, "name": "Lakvision TV", "link": "https://lakvisiontv.net" },
  { "id": 2, "name": "Cartoon Network", "link": "https://cartoonnetwork.com" }
]
```

---

### 4️⃣ Get Specific Channel Programs

Fetch programs from a specific channel by **channel ID**.

**Endpoint:**

```
GET /api/channel/<channel_id>
```

**Example Request:**

```bash
GET https://ginisisila.netlify.app/api/channel/5
```

**Example Response:**

```json
{
  "channel": "Lakvision TV",
  "programs": [
    {
      "title": "Ruby and the Well 60",
      "link": "https://ginisisilacartoon.net/watch.php?id=243093"
    }
  ]
}
```

---

### 5️⃣ Get More Programs List

Fetch additional programs (pagination supported).

**Endpoint:**

```
GET /api/more?url=<more_url>&i=<page_number>
```

**Example Request:**

```bash
GET https://ginisisila.netlify.app/api/more?url=https://lakvisiontv.net/more.php?cat=965&i=2
```

**Example Response:**

```json
{
  "page": 2,
  "results": [
    {
      "title": "Ruby and the Well 61",
      "link": "https://ginisisilacartoon.net/watch.php?id=243094",
      "thumbnail": "https://lakvisiontv.net/thumb2.jpg"
    }
  ]
}
```

> 🔹 Supports `&i=2`, `&i=3`, etc., for multiple pages.

---

## ⚡ Features

* ✅ Search cartoons by name
* ✅ Fetch episode details + embed URL
* ✅ Get all channels & channel programs
* ✅ Support multiple pages for search & more
* ✅ YouTube embed links converted automatically
* 🌍 CORS enabled (works on any website)

---

## 👨‍💻 Creator Info

```json
{
  "creator": "Kawdhitha Nirmal",
  "CodeXSL": "Developer"
}
```

---

## 📝 Notes

* All URLs are **directly fetchable** via API
* Pagination is supported with `&i=<page_number>`
* You can use this API for **web apps, mobile apps, or dashboards**
* No CORS issues (call from any website!)
* 🚀 Fully deployed on **Netlify** for free hosting.
