# AdGuard Home

LazyCat LPK v2 packaging for `adguard/adguardhome:v0.107.78`.

Notes:

- Local Docker is not required.
- Host networking is not used because port `53` is already occupied in the LazyCat environment.
- The container sets `ADGUARD_HOME_DEFAULT_WEB_PORT=80`, so first-time setup and the initialized Web UI both stay behind LazyCat's `http://adguardhome:80/` upstream.
- LazyCat automatic Web health checks are explicitly disabled with `application.health_check.disable: true` and `upstream.disable_auto_health_checking: true`. Neither `3000` nor `80` should gate container startup.
- DHCP `67/68` is intentionally not exposed.
- GitHub Actions uses the `docker.1ms.run` mirror and publishes only to MiaoMiao Store.
- The scheduled workflow uses `update.strategy: publish`: a new upstream version is committed, tagged, released, and submitted without opening a PR.

Required GitHub Secrets:

- `APPSTORE_URL`
- `APPSTORE_TOKEN`
- `APP_ID` (optional when the store can resolve `AdGuard Home` by name)

`LAZYCAT_TOKEN` and official LazyCat store credentials are not used.
