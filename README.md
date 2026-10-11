# DataMine-Archiver

If you found this link in your server logs: this is the crawler that sent the request.

```
User-Agent: DataMine-Archiver/1.0 (+https://github.com/indyraider/datamine-bot)
```

## What it does

It keeps a dated archive of public policy documents so that changes over time can be
looked up later.

- **`/robots.txt`** from roughly 100,000 popular domains (the [Tranco](https://tranco-list.eu/)
  top list) and a list of news and media sites. **Once per day, one request per domain.**
  If `https://` fails it may retry once on `https://www.` or `http://`.
- **A small set of specific public pages**, such as published AI training-data disclosures,
  government rulemaking dockets and state registry listings. Once per day, and only after
  checking that page's `robots.txt`.

It does not log in, submit forms, follow links across your site, or collect personal data.

## How to opt out

For anything other than `/robots.txt`, it obeys your robots.txt:

```
User-agent: DataMine-Archiver
Disallow: /
```

Fetching `/robots.txt` itself is how any crawler reads your rules, so that one daily request
continues. To be removed from the list entirely, [open an issue](../../issues/new) with the
domain and it will be dropped.
