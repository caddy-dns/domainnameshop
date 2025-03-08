# [Domainname.shop](https://domene.shop) DNS module for Caddy

This package contains a DNS provider module for [Caddy](https://github.com/caddyserver/caddy). It can be used to manage DNS records with [Domainname.shop](https://domene.shop).

## Caddy module name

```
dns.providers.domainnameshop
```

## Config examples

To use this module for the ACME DNS challenge, [configure the ACME issuer in your Caddy JSON](https://caddyserver.com/docs/json/apps/tls/automation/policies/issuer/acme/) like so:

```json
{
	"module": "acme",
	"challenges": {
		"dns": {
			"provider": {
				"name": "domainnameshop",
				"api_token": "DOMAINNAMESHOP_API_TOKEN",
				"api_secret": "DOMAINNAMESHOP_API_SECRET"
			}
		}
	}
}
```

or with the Caddyfile:

```
# globally
{
	acme_dns domainnameshop <api_token> <api_secret>
}
```

```
# one site
example.com {
	respond "Hello World" 
	tls {
		dns domainnameshop <api_token> <api_secret>
	}
}

```
