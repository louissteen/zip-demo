# Table of contents

* [API Reference](README.md)

## Getting started <a href="#getting-started" id="getting-started"></a>

* [Authentication](getting-started/authentication.md)
* [Conventions](getting-started/conventions.md)
* [Webhooks](getting-started/webhooks.md)

## Resources <a href="#resources" id="resources"></a>

* [Requests](requests/README.md)
* [Purchase orders](purchase-orders/README.md)
* [Invoices](invoices/README.md)
* [Bills](bills/README.md)
* [Payments](payments/README.md)
* [Vendors](vendors/README.md)
* [Budgets](budgets/README.md)

## Endpoints <a href="#endpoints" id="endpoints"></a>

* ```yaml
  type: builtin:openapi
  props:
    models: true
    downloadLink: true
    grouping: by-tag
  dependencies:
    spec:
      ref:
        kind: openapi
        spec: zip-procurement-v1
  ```
