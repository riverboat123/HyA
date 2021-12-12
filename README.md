##部署
[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://dashboard.heroku.com/new?template=https://github.com/Lbingyi/HerokuXray) 

<details>
<summary>可以使用Cloudflare的Workers来中转流量，2配置为：</summary>

```js
addEventListener(
  "fetch", event => {
    let url = new URL(event.request.url);
    url.host = "xxx.herokuapp.com";
    let request = new Request(url, event.request);
    event.respondWith(
      fetch(request)
    )
  }
)
```
</details>
