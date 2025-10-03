# FSL API

## مرور کلی

این API برای دریافت لیست اخبار از **Hacker News** و همچنین Scrape کردن متن مقالات استفاده می‌شود.  
API در حال حاضر بر روی <a href="https://render.com">Render Service</a> اجرا میشود. هر گونه تغییر از طریق همین Document اعلام خواهد شد.

### Endpoints:  
  - `GET /` → دریافت لینک آخرین اخبار از صفحه اصلی HackerNews  
  - `GET /scrape?url=<article_url>` → دریافت متن کامل مقاله


**`Example Request:`**
```bash
curl -X GET https://fast-api-7gqj.onrender.com/
```

**`Response:`** 
```javascript
{
  "urls": [
    "https://thehackernews.com/2025/08/russian-group-encrypthub-exploits-msc.html",
    "https://thehackernews.com/2025/08/microsoft-discloses-exchange-server.html",
    "https://thehackernews.com/2025/08/zero-trust-ai-privacy-in-age-of-agentic.html"
    ....
  ]
}
```

و بعد از انتخاب لینک مقاله میتوانید آن را Scrape کنید.

### مسیر:

```bash
GET https://fast-api-7gqj.onrender.com/scrape?url=FULL_LINK_HERE
```

### نمونه:

**`Request:`**
```bash
GET https://fast-api-7gqj.onrender.com/scrape?url=https://thehackernews.com/2025/08/russian-group-encrypthub-exploits-msc.html
```

**`Response:`**
```javascript
{
  "content": "The employees in your organization can install ... ",
  "url": "https://thehackernews.com/2025/08/the-wild-west-of-shadow-it.html"
}
```

در کلید `content` متن کامل خبر برگردانده میشود.
کلید `url` لینک وارد شده را مجددا بر میگرداند.
