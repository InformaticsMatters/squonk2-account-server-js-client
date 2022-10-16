# Account Server API JS Client

[![npm version](https://badge.fury.io/js/%40squonk%2Faccount-server-client.svg)](https://badge.fury.io/js/%40squonk%2Faccount-server-client)

This repo is a NodeJS package that generates a typescript client from an open api specification.

- Consumes the Squonk Account Server API
- Generated from the latest OpenAPI tag with [Orval](https://orval.dev)
- Typescript
- Calls made by Axios (this might change)
- Functions to call each API path
- React-Query v4 hooks for use in React applications

Client generated automatically from the OpenAPI with a custom GitHub Action

[Client Generator](https://github.com/InformaticsMatters/openapi-js-client-generator)

## Output

Provides typescript async functions and react hooks. The contents published packages depend on the version of the `openapi.yaml` used to generate it. In general though, the package is organised as follows:

All types can be imported from the main entry point:
```ts
import type { OrganisationDetail, UnitDetail, ... } from '@squonk/account-server-client';
```

The custom instance (what is used to make all Axios calls) can also be imported from here:

```ts
import { customInstance } from '@squonk/account-server-client';
```

Each `tag` from the `openapi.yaml` is used to create a sub-entry point. For example, the functions to make requests and the `react-query` hooks for a `unit` tag can be imported as follows:

```ts
import { useGetOrganisationUnits, getGetOrganisationUnitsQueryKey, ... } from '@squonk/account-server-client/dataset';
```
