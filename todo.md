# Todo List

- [ ] Add [AES encryption][h], or port samples to [CryptoDomeX][i]
- [ ] Cleaner update of UID across all my GPG keys
- [ ] Add python `unittest`
- [ ] Add [read-the-docs via sphinx][k]

## Publish to Github

1. Create a new repo at `github.com/new`
2. Clone repo locally
3. Add files as needed
3. Run isort `isort .`
4. Run black `black --config .black .`
5. Run flake8 `flake8`
4. Commit and push back to github
10. [Publish to PyPi][l]
10. Create a `release-0.0.2.md` file
10. Create new release: https://github.com/brianddk/pyexch/releases/new
11. Input release notes
12. Attach `dist` files and sigs

## Publish on PyPi

1. Upgrade all `python -m pip install --upgrade pip setuptools build twine`
6. Build distribution `python -m build && cd dist`
7. Sign `for %p in (*0.0.2*.gz *0.0.2*.whl) do gpg -bau brianddk -o %p.sig %p`
8. Verify `for %p in (*0.0.2*.sig) do gpg --verify %p`
9. Export `gpg -ao brianddk.asc --export brianddk`
10. Test publish: `python -m twine upload --repository testpypi *.whl *.gz`
11. Test install: `python -m pip install --index-url https://test.pypi.org/simple/ --no-deps pyexch`
12. Publish: `python -m twine upload *.whl *.gz`


<!-- Links -->

[a]: https://docs.python.org/3.12/library/collections.html#collections.OrderedDict (OrderedDict)
[b]: https://github.com/Kijewski/pyjson5 (JSON5)
[c]: https://packaging.python.org/en/latest/tutorials/packaging-projects/ (PyPi)
[d]: https://forums.coinbasecloud.dev/t/did-oauth2-revoke-uri-stop-doing-work/7394 (Revoke URI)
[e]: templates
[f]: templates/trezor_ks.json5
[g]: templates/json_ks.json5
[h]: https://stackoverflow.com/a/21928790/4634229 (AES encryption)
[i]: https://stackoverflow.com/a/48175912/4634229 (CryptoDomeX)
[j]: #publish-to-github
[k]: https://docs.readthedocs.io/en/stable/tutorial/index.html (RTD Tutorial)
[l]: #publish-to-pypi
[m]: https://docs.cloud.coinbase.com/sign-in-with-coinbase/docs/sign-in-with-coinbase-2fa
[n]: https://github.com/brianddk/pyexch/issues/13
[o]: https://github.com/brianddk/pyexch/issues/10
[p]: https://github.com/brianddk/pyexch/issues/9
[q]: #pr-to-coinbase-python-py
[r]: 
[s]: 
[t]: 
[u]: 
[v]: 
[w]: 
[x]: 
[y]: 
[z]: 
[0]: 
[1]: 
[2]: 
[3]: 
[4]: 
[5]: 
[6]: 
[7]: 
[8]: 
[9]: 

