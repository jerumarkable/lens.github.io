# Getting Started

To get things started, you’ll need a `client_access_token` to make image search requests to Lens API. If you don’t have one, please reach out to support@markable.ai. Once you have one, you’ll be able to search an image against our public catalogs with millions of items.

To make a search request you’ll need:
- `image_uri` (http, data string, blob)
- `client_access_token`
- Catalog `_id` or `name`

A typical search request using the JavaScript Fetch API can look like this:

```const accessToken = “123abc”
const searchUrl = “https://catalog.markable.ai/image/search”

const { data } =  await fetch(searchUrl, {
    method: ‘POST’,
    headers: {
        ‘Content-Type’: ‘application/json’,
        ‘Authorization’: `Bearer ${accessToken}`
    },
    body: JSON.stringify({ 
        data: { 
            image_uri: “https://www.google.com/image/1”,
            catalogs: [ { name: ‘catalog-1’ }, { name: ‘catalog-2’}, { name: ‘catalog-3’ } ]
        }
    })
}).then(res => res.json())

console.log(data)
```
