# `ansible-role-httpd`: install HTTPd server

This [Ansible](https://www.ansible.com) role aims at installing the [Apache HTTPd](https://httpd.apache.org/) [HTTP](https://fr.wikipedia.org/wiki/Hypertext_Transfer_Protocol) server on RHEL/CentOS.

## Role variables

### `mod_headers`

 - `httpd_headers_xss_protection: "1; mode=block"`: sets the [`X-XSS-Protection`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-XSS-Protection) header.
 - `httpd_headers_x_content_type_options: "nosniff"`: sets the [`X-Content-Type-Options`](https://developer.mozilla.org/fr/docs/Web/HTTP/Headers/X-Content-Type-Options) header.
 - `httpd_headers_referer_policy: "strict-origin"`: sets the [`Referrer-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referrer-Policy) header.
 - `httpd_headers_csp: ""`: sets the [`Content-Security-Policy`](https://developer.mozilla.org/fr/docs/Web/HTTP/CSP) header. This is **undefined by default**.
 - `httpd_headers_xframe_options: "SAMEORIGIN"`: sets the [`X-Frame-Options`](https://developer.mozilla.org/fr/docs/Web/HTTP/Headers/X-Frame-Options) header.
 - `httpd_headers_feature_policy: ""`: sets the [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) header. This is **undefined by default**.
 - `httpd_headers_hsts: "max-age=15552001; includeSubDomains;"`: sets the [HTTP Strict Transport Security](https://developer.mozilla.org/fr/docs/S%C3%A9curit%C3%A9/HTTP_Strict_Transport_Security) header.

### `mod_ssl`

 - `httpd_ssl_honor_cipher: "on"`: sets the [`SSLHonorCipherOrder`](https://httpd.apache.org/docs/current/fr/mod/mod_ssl.html#sslhonorcipherorder) option.
 - `httpd_ssl_protocol`: sets the [`SSLProtocol`](https://httpd.apache.org/docs/2.4/fr/mod/mod_ssl.html#sslprotocol) option. This is **undefined by default**.
 - `httpd_ssl_cipher_suite`: sets the [`SSLCipherSuite`](https://httpd.apache.org/docs/2.4/fr/mod/mod_ssl.html#sslciphersuite) option. This is **undefined by default**.

 Please, refer to the [HTTPd document on TLS encryption](https://httpd.apache.org/docs/2.4/en/ssl/ssl_howto.html) and take a look at the [Mozilla SSL Configuration Generator](https://ssl-config.mozilla.org/).

### `mod_security`

- `httpd_security_server_tokens: "Prod"`: sets the [`ServerTokens`](https://httpd.apache.org/docs/2.4/mod/core.html#servertokens) option.
- `httpd_security_signature: "Off"`: sets the [`ServerSignature`](https://httpd.apache.org/docs/2.4/mod/core.html#servertokens) option.
- `httpd_security_secserver_signature: ""`: sets the `SecServerSignature` within from the `security2_module`.
