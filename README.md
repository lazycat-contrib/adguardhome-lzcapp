# AdGuard Home

LazyCat LPK v2 packaging for `adguard/adguardhome:v0.107.78`.

Notes:

- Local Docker is not required.
- Host networking is not used because port `53` is already occupied in the LazyCat environment.
- Web admin remains on port `3000` during first-time setup.
- DHCP `67/68` is intentionally not exposed.
- GitHub Actions uses the `docker.1ms.run` mirror and publishes only to MiaoMiao Store.
- The scheduled workflow uses `update.strategy: publish`: a new upstream version is committed, tagged, released, and submitted without opening a PR.

Required GitHub Secrets:

- `APPSTORE_URL`
- `APPSTORE_TOKEN`
- `APP_ID` (optional when the store can resolve `AdGuard Home` by name)

`LAZYCAT_TOKEN` and official LazyCat store credentials are not used.
