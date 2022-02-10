[@tauri-apps/api](../index.md) / [shell](../modules/shell.md) / Child

# Class: Child

[shell](../modules/shell.md).Child

## Constructors

### constructor

• **new Child**(`pid`)

#### Parameters

| Name | Type |
| :------ | :------ |
| `pid` | `number` |

#### Defined in

[shell.ts:134](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/shell.ts#L134)

## Properties

### pid

• **pid**: `number`

The child process `pid`.

#### Defined in

[shell.ts:132](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/shell.ts#L132)

## Methods

### kill

▸ **kill**(): `Promise`<`void`\>

Kills the child process.

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Defined in

[shell.ts:169](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/shell.ts#L169)

___

### write

▸ **write**(`data`): `Promise`<`void`\>

Writes `data` to the `stdin`.

**`example`**
```typescript
const command = new Command('node')
const child = await command.spawn()
await child.write('message')
await child.write([0, 1, 2, 3, 4, 5])
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `data` | `string` \| `Uint8Array` | The message to write, either a string or a byte array. |

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Defined in

[shell.ts:152](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/shell.ts#L152)
