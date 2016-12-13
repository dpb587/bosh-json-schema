# bosh-json-schema

Some schemas for sanity.

 * Base URI - [https://dpb587.github.io/bosh-json-schema/](https://dpb587.github.io/bosh-json-schema/)
 * Repository [https://github.com/dpb587/bosh-json-schema](https://github.com/dpb587/bosh-json-schema)


## Directory Layout

Top level is a `v0` directory - the zero version is [JSON Schema](http://json-schema.org/)-based and may change.

The `cpi` directory contains CPI-related schemas.

 * `cpi/(disk|network|vm).json` - refer to the latest CPI version for each resource (e.g. [`cpi/vm.json`](v0/cpi/disk.json))
 * `cpi/{cpi-name}/{cpi-version}/(disk|network|vm).json` - cloud property declarations for CPI `cpi-name`. Version-specific schemas are not committed so `v0` means roughly the latest CPI supported properties (e.g. [`cpi/aws/v0/disk.json`](v0/cpi/aws/v0/disk.json))

The `director/{director-version}` directory contains director-related schemas. Version-specific schemas are not committed so `v0` means roughly the latest director supported properties.

 * `(cloud-config|deployment-v2|runtime-config).json` (e.g. [`deployment-v2.json`](v0/director/v0/deployment-v2.json))
 * `network/(manual|vip).json` (e.g. [`network/manual.json`](v0/director/v0/network/manual.json))


## Futures

 * files aren't fully validated and are a collection from a few side projects and iterations
 * every type which may have a non-standard value or custom restrictions (e.g. IP address) should be a separate type instead of `string`
 * `cpi/*.json` is just convenience; your JSON resolver should know which CPI to load
 * [ref](https://github.com/dpb587/bosh-veneer-release/tree/a4bc6196257c077f19943542b5fde55c9637d8c4/src/webapp/src/veneer-core-bundle/src/Service/JsonSchema)


## License

[MIT License](LICENSE)
