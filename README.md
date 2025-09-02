# convert-copy-as-curl

convert "copy as cURL" within Google Chrome DevTools

## curl-config

Extract cookies and headers from "copy as cURL" and convert to curl config format.

```sh
$ pbpaste | ./curl-config | tee curl-config.txt
header = "accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7"
header = "accept-language: ja,en-US;q=0.9,en;q=0.8"
header = "cache-control: no-cache"
header = "pragma: no-cache"
header = "priority: u=0, i"
header = "sec-ch-ua: \"Not;A=Brand\";v=\"99\", \"Google Chrome\";v=\"139\", \"Chromium\";v=\"139\""
header = "sec-ch-ua-mobile: ?0"
header = "sec-ch-ua-platform: \"macOS\""
header = "sec-fetch-dest: document"
header = "sec-fetch-mode: navigate"
header = "sec-fetch-site: none"
header = "sec-fetch-user: ?1"
header = "upgrade-insecure-requests: 1"
header = "user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/139.0.0.0 Safari/537.36"
```

```sh
$ curl --config curl-config.txt https://example.com/ # re-use cookies and headers
```

## License

The MIT license
