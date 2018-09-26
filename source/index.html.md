---
title: Bancor

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - javascript
#  - ruby
#  - python

toc_footers:
  - <a href='#'>Sign Up for a Developer Account</a>

includes:
  - price_ticker
  - available_pairs
  - token_data
  - price_discovery
  - convert_api
  - errors

search: true
---

# Introduction

Welcome to the Bancor API Docs.  This site is in development.  Authentication coming soon.

Bancor provides public API methods which take HTTP GET requests and return JSON.

Please note that making more than 6 calls per second to the public API, or repeatedly and needlessly fetching excessive amounts of data, can result in your IP being banned.

# Authentication (Soon)

Bancor uses API keys to allow access to the API. You can register a new Bancor API key at our [developer portal](http://bancor.network/developers).

Bancor expects the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: bancorkeyhere`

<aside class="notice">
You must replace <code>bancorkeyhere</code> with your personal API key.
</aside>
