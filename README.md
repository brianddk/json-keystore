# json-keystore

[![PyPI version](https://badge.fury.io/py/json-keystore.svg)](https://badge.fury.io/py/json-keystore)
[![License](https://img.shields.io/badge/License-Apache%202.0-green.svg)](https://opensource.org/license/apache-2-0/)
[![GitHub](https://img.shields.io/badge/GitHub-Repo-blue.svg)](https://github.com/brianddk/json-keystore)
[![GitHub Discussions](https://img.shields.io/badge/GitHub-Discussions-blue.svg)](https://github.com/brianddk/json-keystore/discussions)
[![Donate with Bitcoin Lightning](https://img.shields.io/badge/Donate-Lightning-yellow.svg)](https://tippin.me/@dkbriand)
[![Donate with Bitcoin](https://img.shields.io/badge/Donate-Bitcoin-orange.svg)](https://mempool.space/address/bc1qwc2203uym96u0nmq04pcgqfs9ldqz9l3mz8fpj)

***EARLY PREVIEW RELEASE*** of a rudimentary python library for encrypted JSON

## Future Plans

- [ ] Add [AES encryption][n], or port samples to [CryptoDomeX][o]

## Install and Initial Setup

This utility allows you to set up an encrypted JSON keystore that supports both GPG and Trezor-CipherKeyValue encryption.  You will need either a GPG key pair installed, or a Trezor attached.  As a fallback you can store data in naked JSON, but that is obviously not recommended.

### Install with Debug support

If you want to debug one of the client calls or step into a [trezorlib][j] call, you can install from GIT sources.  Then you can add breakpoints in source using calls to `breakpoint()` to get more detailed information.

1. Get source: `git clone https://github.com/brianddk/json-keystore.git`
2. Switch directories: `cd json-keystore`
3. Upgrade setuptools: `python -m pip install --upgrade setuptools pip wheel`
3. Install develop mode via pip: `pip install -e .`
4. Verify install: `python -c "import json_keystore"`
5. Optionally add `breakpoint()` into one of the `*.py` files
6. Optionally step through code in the python debugger (`pdb`)

### Install without GIT

To install the most recent edition directly from GitHub tarball:

```
python -m pip install --upgrade setuptools pip wheel
python -m pip install git+https://github.com/brianddk/json-keystore.git
```

You won't get to documentation or templates, but all the code will land and function

### Install last release from PIP

1. Upgrade: `python -m pip install --upgrade setuptools pip wheel`
2. Install: `pip install json-keystore`
2. Verify install: `python -c "import json_keystore"`

## Building a Keystore

Template keystores are provided in the [templates][v] directory.  If you decide to use a naked JSON, you can simply modify the `null` values in the `json_ks.json` to fill in the key values.  If you want to use encryption you will need to modify on of the encryption templates (`trezor_ks.json` or `gnupg_ks.json`) and update the unencrypted parameters.  These all deal with various encryption settings.  Note that for Trezor, `zlib` is the ONLY supported compression.  Since the JSON keystore is self explanatory, I'll focus on building the encrypted keystores.

### Building a GnuPG encrypted Keystore:

Start with the GnuPG template `gnupg_ks.json`, and change the recipient to the key-id of your GnuPG key.  This can be the UID (email), or the short or long key hex.

```
{
  "format": "gnupg",
  "gnupg": {
    "recipient": "TYPE_YOUR_GPG_PUBLIC_KEY_HERE"
  }
}
```


<!-- Link Nest -->

[a]: https://docs.cloud.coinbase.com/sign-in-with-coinbase (api v2)
[b]: https://docs.cloud.coinbase.com/advanced-trade-api (api v3)
[c]: https://github.com/coinbase/coinbase-python/blob/master/README.rst#usage (client v2)
[d]: https://coinbase.github.io/coinbase-advanced-py/coinbase.rest.html#module-coinbase.rest.accounts (client v3)
[e]: https://docs.cloud.coinbase.com/sign-in-with-coinbase/docs/api-users#show-authorization-information
[f]: https://github.com/coinbase/coinbase-python#usage
[g]: https://github.com/Kijewski/pyjson5 (JSON5)
[h]: https://github.com/coinbase/coinbase-python/?tab=readme-ov-file#oauth2
[i]: https://github.com/coinbase/coinbase-python/?tab=readme-ov-file#api-key--secret
[j]: https://pypi.org/project/trezor/
[k]: https://github.com/coinbase/coinbase-python/?tab=readme-ov-file#usage
[l]: https://coinbase.github.io/coinbase-advanced-py/coinbase.rest.html#restclient-constructor
[m]: https://coinbase.github.io/coinbase-advanced-py/index.html
[n]: https://stackoverflow.com/a/21928790/4634229
[o]: https://stackoverflow.com/a/48175912/4634229
[p]: https://github.com/coinbase/coinbase-python/?tab=readme-ov-file#market-data
[q]: https://github.com/coinbase/coinbase-python/ (coinbase-python)
[r]: https://github.com/coinbase/coinbase-advanced-py (coinbase-advanced-py)
[s]: https://docs.cloud.coinbase.com/sign-in-with-coinbase/docs/changelog#2024-apr-02 (april-2nd)
[t]: https://portal.cloud.coinbase.com/access/api?keyType=trade&referrer=advanced_trade (v3-api-keys)
[u]: https://www.coinbase.com/settings/api (oauth2-api-keys)
[v]: templates
[w]: https://docs.cloud.coinbase.com/sign-in-with-coinbase/docs/welcome (siwc-spec)
[x]: https://docs.cloud.coinbase.com/advanced-trade-api/docs/welcome (at-spec)
[y]: https://github.com/coinbase/coinbase-python/?tab=readme-ov-file#usage (v2-lib-doc)
[z]: https://coinbase.github.io/coinbase-advanced-py/ (v3-lib-doc)
[0]: https://docs.python.org/3.12/tutorial/index.html (py3-tutorial)



