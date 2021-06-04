# HTTP Caching

HTTP has two concepts for caching Freshness and Validation. 

## Freshness

[Freshness](https://developer.mozilla.org/en-US/docs/Web/HTTP/Caching#freshness) determines if a resources is fresh or stale. How to handle cached resources and when resources should considered stale is set by the [`Cache-Control`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cache-Control) and [`Expires`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Expires) headers. 

```http
Cache-Control: public 
Expires: Wed, 21 Oct 2015 07:28:00 GMT
```

## Validation 

[Validation](https://developer.mozilla.org/en-US/docs/Web/HTTP/Caching#cache_validation) can be strong or weak.

The [`E-Tag`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/ETag) header can be used for strong validation.

The `Last-Modified` can be used for weak validation (weak because it has a resolution of 1 second).

When valid, a response can return a `304` status without a body to instruct the cache to use cached copy, thus saving bandwidth.