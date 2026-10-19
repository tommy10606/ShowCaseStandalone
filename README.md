# ShowCaseStandalone

## Maintained Paper version 3.0.1

Maintained by Tommy10606 for **Paper 26.3 build 205**, using the pinned
`io.papermc.paper:paper-api:26.3.build.205-stable` API and Java 25.
Original authors and their copyright notices are retained. See [NOTICE](NOTICE)
and [CHANGELOG.md](CHANGELOG.md).

### Install

1. Stop the server and back up the current plugin JAR and the entire
   `plugins/ShowCaseStandalone/` folder.
2. Replace the old ShowCaseStandalone JAR with `ShowCaseStandalone-3.0.1.jar`;
   keep only one copy of the plugin in `plugins/`.
3. Keep the existing configuration and shop files in place, then start normally.

The existing shop storage versions and serialization aliases are unchanged.
Verify purchases, sales, item metadata, and restart persistence on a test copy
before replacing a production installation. Old data that Bukkit itself cannot
read may still require migration separately.

### Build

Use **JDK 25** and **Maven 3.9 or later**:

```sh
mvn -B -ntp verify
```

The compiled plugin is `target/ShowCaseStandalone-3.0.1.jar`. Optional integration
JARs in `lib/` are the original upstream compile-only dependencies; they are
not included in the plugin JAR and keep their own licenses. Vault, EssentialsX,
WorldGuard, and WorldEdit APIs are also compile-only dependencies.
The tests use MockBukkit 26.3 and do not contact a running Minecraft server.

### Update checks

The plugin checks the latest published stable release at
https://github.com/tommy10606/ShowCaseStandalone/releases/latest once per
startup, about one second after enabling. The HTTP request runs asynchronously,
uses bounded timeouts, and reports status only to the server console. There is
no polling, automatic download, or automatic installation. A failed request is
retried at the next startup. The pending task is cancelled on disable.

The following setting is added automatically to existing configurations:

```yaml
update-checker:
  enabled: true
```

Set it to `false` to disable checks, then restart. Publish releases with stable
semantic version tags such as `v3.0.1` or `v3.0.2`; drafts, prereleases, and
standalone Git tags are not treated as published stable releases. With no public
release yet, the console reports that update status is unknown.

### Item names

Use current item names, such as `yellow_wool`, `oak_log`, or
`minecraft:diamond`. Historical numeric block variants such as `WOOL:4`
are not converted through CraftLegacy. A numeric damage suffix such as
`diamond_pickaxe:5` is supported for damageable items.

---



## License
This project is licensed under [GPLv3](LICENSE) 


### Libraries / Dependencies
Binaries and other files located at lib/ are plugins and/or projects
of other authors. The license might differ. They are only included for
the java compiler to be able to resolve the dependencies and are not
included in the compiled output file.
