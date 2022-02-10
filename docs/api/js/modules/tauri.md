[@tauri-apps/api](../index.md) / tauri

# Namespace: tauri

Invoke your custom commands.

This package is also accessible with `window.__TAURI__.tauri` when `tauri.conf.json > build > withGlobalTauri` is set to true.

## Interfaces

- [InvokeArgs](../interfaces/tauri.InvokeArgs.md)

## Functions

### convertFileSrc

▸ **convertFileSrc**(`filePath`): `string`

Convert a device file path to an URL that can be loaded by the webview.
Note that `asset:` and `https://asset.localhost` must be allowed on the `csp` value configured on `tauri.conf.json > tauri > security`.
Example CSP value: `"csp": "default-src 'self'; img-src 'self' asset: https://asset.localhost"`.

Additionally, the `asset` must be allowlisted under `tauri.conf.json > tauri > allowlist > protocol`,
and its access scope must be defined on the `assetScope` array on the same `protocol` object.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `filePath` | `string` | the file path. |

#### Returns

`string`

the URL that can be used as source on the webview.

#### Defined in

[tauri.ts:100](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/tauri.ts#L100)

___

### invoke

▸ **invoke**<`T`\>(`cmd`, `args?`): `Promise`<`T`\>

Sends a message to the backend.

#### Type parameters

| Name |
| :------ |
| `T` |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `cmd` | `string` | The command name. |
| `args` | [`InvokeArgs`](../interfaces/tauri.InvokeArgs.md) | The optional arguments to pass to the command. |

#### Returns

`Promise`<`T`\>

A promise resolving or rejecting to the backend response.

#### Defined in

[tauri.ts:68](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/tauri.ts#L68)

___

### transformCallback

▸ **transformCallback**(`callback?`, `once?`): `number`

Transforms a callback function to a string identifier that can be passed to the backend.
The backend uses the identifier to `eval()` the callback.

#### Parameters

| Name | Type | Default value |
| :------ | :------ | :------ |
| `callback?` | (`response`: `any`) => `void` | `undefined` |
| `once` | `boolean` | `false` |

#### Returns

`number`

A unique identifier associated with the callback function.

#### Defined in

[tauri.ts:34](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/tauri.ts#L34)
