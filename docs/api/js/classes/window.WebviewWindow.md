[@tauri-apps/api](../index.md) / [window](../modules/window.md) / WebviewWindow

# Class: WebviewWindow

[window](../modules/window.md).WebviewWindow

Create new webview windows and get a handle to existing ones.

**`example`**
```typescript
// loading embedded asset:
const webview = new WebviewWindow('theUniqueLabel', {
  url: 'path/to/page.html'
})
// alternatively, load a remote URL:
const webview = new WebviewWindow('theUniqueLabel', {
  url: 'https://github.com/tauri-apps/tauri'
})

webview.once('tauri://created', function () {
 // webview window successfully created
})
webview.once('tauri://error', function (e) {
 // an error happened creating the webview window
})

// emit an event to the backend
await webview.emit("some event", "data")
// listen to an event from the backend
const unlisten = await webview.listen("event name", e => {})
unlisten()
```

## Hierarchy

- [`WindowManager`](window.WindowManager.md)

  ↳ **`WebviewWindow`**

## Constructors

### constructor

• **new WebviewWindow**(`label`, `options?`)

Creates a new WebviewWindow.
* @param label The webview window label. It must be alphanumeric.

#### Parameters

| Name | Type |
| :------ | :------ |
| `label` | `string` |
| `options` | [`WindowOptions`](../interfaces/window.WindowOptions.md) |

#### Overrides

[WindowManager](window.WindowManager.md).[constructor](window.WindowManager.md#constructor)

#### Defined in

[window.ts:1100](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L1100)

## Properties

### label

• **label**: `string`

Window label.

#### Inherited from

[WindowManager](window.WindowManager.md).[label](window.WindowManager.md#label)

#### Defined in

[window.ts:227](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L227)

___

### listeners

• **listeners**: `Object`

Local event listeners.

#### Index signature

▪ [key: `string`]: [`EventCallback`](../modules/event.md#eventcallback)<`any`\>[]

#### Inherited from

[WindowManager](window.WindowManager.md).[listeners](window.WindowManager.md#listeners)

#### Defined in

[window.ts:229](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L229)

## Methods

### \_handleTauriEvent

▸ **_handleTauriEvent**<`T`\>(`event`, `handler`): `boolean`

#### Type parameters

| Name |
| :------ |
| `T` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `string` |
| `handler` | [`EventCallback`](../modules/event.md#eventcallback)<`T`\> |

#### Returns

`boolean`

#### Inherited from

[WindowManager](window.WindowManager.md).[_handleTauriEvent](window.WindowManager.md#_handletaurievent)

#### Defined in

[window.ts:293](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L293)

___

### center

▸ **center**(): `Promise`<`void`\>

Centers the window.

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Inherited from

[WindowManager](window.WindowManager.md).[center](window.WindowManager.md#center)

#### Defined in

[window.ts:487](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L487)

___

### close

▸ **close**(): `Promise`<`void`\>

Closes the window.

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Inherited from

[WindowManager](window.WindowManager.md).[close](window.WindowManager.md#close)

#### Defined in

[window.ts:733](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L733)

___

### emit

▸ **emit**(`event`, `payload?`): `Promise`<`void`\>

Emits an event to the backend, tied to the webview window.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `event` | `string` | Event name. Must include only alphanumeric characters, `-`, `/`, `:` and `_`. |
| `payload?` | `unknown` | Event payload. |

#### Returns

`Promise`<`void`\>

#### Inherited from

[WindowManager](window.WindowManager.md).[emit](window.WindowManager.md#emit)

#### Defined in

[window.ts:282](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L282)

___

### hide

▸ **hide**(): `Promise`<`void`\>

Sets the window visibility to false.

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Inherited from

[WindowManager](window.WindowManager.md).[hide](window.WindowManager.md#hide)

#### Defined in

[window.ts:713](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L713)

___

### innerPosition

▸ **innerPosition**(): `Promise`<[`PhysicalPosition`](window.PhysicalPosition.md)\>

The position of the top-left hand corner of the window's client area relative to the top-left hand corner of the desktop.

#### Returns

`Promise`<[`PhysicalPosition`](window.PhysicalPosition.md)\>

#### Inherited from

[WindowManager](window.WindowManager.md).[innerPosition](window.WindowManager.md#innerposition)

#### Defined in

[window.ts:330](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L330)

___

### innerSize

▸ **innerSize**(): `Promise`<[`PhysicalSize`](window.PhysicalSize.md)\>

The physical size of the window's client area.
The client area is the content of the window, excluding the title bar and borders.

#### Returns

`Promise`<[`PhysicalSize`](window.PhysicalSize.md)\>

#### Inherited from

[WindowManager](window.WindowManager.md).[innerSize](window.WindowManager.md#innersize)

#### Defined in

[window.ts:365](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L365)

___

### isDecorated

▸ **isDecorated**(): `Promise`<`boolean`\>

Gets the window's current decorated state.

#### Returns

`Promise`<`boolean`\>

#### Inherited from

[WindowManager](window.WindowManager.md).[isDecorated](window.WindowManager.md#isdecorated)

#### Defined in

[window.ts:432](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L432)

___

### isFullscreen

▸ **isFullscreen**(): `Promise`<`boolean`\>

Gets the window's current fullscreen state.

#### Returns

`Promise`<`boolean`\>

#### Inherited from

[WindowManager](window.WindowManager.md).[isFullscreen](window.WindowManager.md#isfullscreen)

#### Defined in

[window.ts:400](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L400)

___

### isMaximized

▸ **isMaximized**(): `Promise`<`boolean`\>

Gets the window's current maximized state.

#### Returns

`Promise`<`boolean`\>

#### Inherited from

[WindowManager](window.WindowManager.md).[isMaximized](window.WindowManager.md#ismaximized)

#### Defined in

[window.ts:416](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L416)

___

### isResizable

▸ **isResizable**(): `Promise`<`boolean`\>

Gets the window's current resizable state.

#### Returns

`Promise`<`boolean`\>

#### Inherited from

[WindowManager](window.WindowManager.md).[isResizable](window.WindowManager.md#isresizable)

#### Defined in

[window.ts:448](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L448)

___

### isVisible

▸ **isVisible**(): `Promise`<`boolean`\>

Gets the window's current visible state.

#### Returns

`Promise`<`boolean`\>

#### Inherited from

[WindowManager](window.WindowManager.md).[isVisible](window.WindowManager.md#isvisible)

#### Defined in

[window.ts:464](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L464)

___

### listen

▸ **listen**<`T`\>(`event`, `handler`): `Promise`<[`UnlistenFn`](../modules/event.md#unlistenfn)\>

Listen to an event emitted by the backend that is tied to the webview window.

#### Type parameters

| Name |
| :------ |
| `T` |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `event` | [`EventName`](../modules/event.md#eventname) | Event name. Must include only alphanumeric characters, `-`, `/`, `:` and `_`. |
| `handler` | [`EventCallback`](../modules/event.md#eventcallback)<`T`\> | Event handler. |

#### Returns

`Promise`<[`UnlistenFn`](../modules/event.md#unlistenfn)\>

A promise resolving to a function to unlisten to the event.

#### Inherited from

[WindowManager](window.WindowManager.md).[listen](window.WindowManager.md#listen)

#### Defined in

[window.ts:244](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L244)

___

### maximize

▸ **maximize**(): `Promise`<`void`\>

Maximizes the window.

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Inherited from

[WindowManager](window.WindowManager.md).[maximize](window.WindowManager.md#maximize)

#### Defined in

[window.ts:593](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L593)

___

### minimize

▸ **minimize**(): `Promise`<`void`\>

Minimizes the window.

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Inherited from

[WindowManager](window.WindowManager.md).[minimize](window.WindowManager.md#minimize)

#### Defined in

[window.ts:653](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L653)

___

### once

▸ **once**<`T`\>(`event`, `handler`): `Promise`<[`UnlistenFn`](../modules/event.md#unlistenfn)\>

Listen to an one-off event emitted by the backend that is tied to the webview window.

#### Type parameters

| Name |
| :------ |
| `T` |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `event` | `string` | Event name. Must include only alphanumeric characters, `-`, `/`, `:` and `_`. |
| `handler` | [`EventCallback`](../modules/event.md#eventcallback)<`T`\> | Event handler. |

#### Returns

`Promise`<[`UnlistenFn`](../modules/event.md#unlistenfn)\>

A promise resolving to a function to unlisten to the event.

#### Inherited from

[WindowManager](window.WindowManager.md).[once](window.WindowManager.md#once)

#### Defined in

[window.ts:265](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L265)

___

### outerPosition

▸ **outerPosition**(): `Promise`<[`PhysicalPosition`](window.PhysicalPosition.md)\>

The position of the top-left hand corner of the window relative to the top-left hand corner of the desktop.

#### Returns

`Promise`<[`PhysicalPosition`](window.PhysicalPosition.md)\>

#### Inherited from

[WindowManager](window.WindowManager.md).[outerPosition](window.WindowManager.md#outerposition)

#### Defined in

[window.ts:346](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L346)

___

### outerSize

▸ **outerSize**(): `Promise`<[`PhysicalSize`](window.PhysicalSize.md)\>

The physical size of the entire window.
These dimensions include the title bar and borders. If you don't want that (and you usually don't), use inner_size instead.

#### Returns

`Promise`<[`PhysicalSize`](window.PhysicalSize.md)\>

#### Inherited from

[WindowManager](window.WindowManager.md).[outerSize](window.WindowManager.md#outersize)

#### Defined in

[window.ts:384](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L384)

___

### requestUserAttention

▸ **requestUserAttention**(`requestType`): `Promise`<`void`\>

 Requests user attention to the window, this has no effect if the application
is already focused. How requesting for user attention manifests is platform dependent,
see `UserAttentionType` for details.

Providing `null` will unset the request for user attention. Unsetting the request for
user attention might not be done automatically by the WM when the window receives input.

#### Platform-specific

- **macOS:** `null` has no effect.
- **Linux:** Urgency levels have the same effect.

#### Parameters

| Name | Type |
| :------ | :------ |
| `requestType` | ``null`` \| [`UserAttentionType`](../enums/window.UserAttentionType.md) |

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Inherited from

[WindowManager](window.WindowManager.md).[requestUserAttention](window.WindowManager.md#requestuserattention)

#### Defined in

[window.ts:518](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L518)

___

### scaleFactor

▸ **scaleFactor**(): `Promise`<`number`\>

The scale factor that can be used to map physical pixels to logical pixels.

#### Returns

`Promise`<`number`\>

#### Inherited from

[WindowManager](window.WindowManager.md).[scaleFactor](window.WindowManager.md#scalefactor)

#### Defined in

[window.ts:314](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L314)

___

### setAlwaysOnTop

▸ **setAlwaysOnTop**(`alwaysOnTop`): `Promise`<`void`\>

Whether the window should always be on top of other windows.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `alwaysOnTop` | `boolean` | Whether the window should always be on top of other windows or not. |

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Inherited from

[WindowManager](window.WindowManager.md).[setAlwaysOnTop](window.WindowManager.md#setalwaysontop)

#### Defined in

[window.ts:776](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L776)

___

### setDecorations

▸ **setDecorations**(`decorations`): `Promise`<`void`\>

Whether the window should have borders and bars.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `decorations` | `boolean` | Whether the window should have borders and bars. |

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Inherited from

[WindowManager](window.WindowManager.md).[setDecorations](window.WindowManager.md#setdecorations)

#### Defined in

[window.ts:754](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L754)

___

### setFocus

▸ **setFocus**(): `Promise`<`void`\>

Bring the window to front and focus.

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Inherited from

[WindowManager](window.WindowManager.md).[setFocus](window.WindowManager.md#setfocus)

#### Defined in

[window.ts:984](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L984)

___

### setFullscreen

▸ **setFullscreen**(`fullscreen`): `Promise`<`void`\>

Sets the window fullscreen state.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `fullscreen` | `boolean` | Whether the window should go to fullscreen or not. |

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Inherited from

[WindowManager](window.WindowManager.md).[setFullscreen](window.WindowManager.md#setfullscreen)

#### Defined in

[window.ts:963](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L963)

___

### setIcon

▸ **setIcon**(`icon`): `Promise`<`void`\>

Sets the window icon.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `icon` | `string` \| `Uint8Array` | Icon bytes or path to the icon file. |

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Inherited from

[WindowManager](window.WindowManager.md).[setIcon](window.WindowManager.md#seticon)

#### Defined in

[window.ts:1005](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L1005)

___

### setMaxSize

▸ **setMaxSize**(`size`): `Promise`<`void`\>

Sets the window maximum inner size. If the `size` argument is undefined, the constraint is unset.

**`example`**
```typescript
import { appWindow, LogicalSize } from '@tauri-apps/api/window'
await appWindow.setMaxSize(new LogicalSize(600, 500))
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `size` | `undefined` \| ``null`` \| [`PhysicalSize`](window.PhysicalSize.md) \| [`LogicalSize`](window.LogicalSize.md) | The logical or physical inner size, or `null` to unset the constraint. |

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Inherited from

[WindowManager](window.WindowManager.md).[setMaxSize](window.WindowManager.md#setmaxsize)

#### Defined in

[window.ts:883](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L883)

___

### setMinSize

▸ **setMinSize**(`size`): `Promise`<`void`\>

Sets the window minimum inner size. If the `size` argument is not provided, the constraint is unset.

**`example`**
```typescript
import { appWindow, PhysicalSize } from '@tauri-apps/api/window'
await appWindow.setMinSize(new PhysicalSize(600, 500))
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `size` | `undefined` \| ``null`` \| [`PhysicalSize`](window.PhysicalSize.md) \| [`LogicalSize`](window.LogicalSize.md) | The logical or physical inner size, or `null` to unset the constraint. |

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Inherited from

[WindowManager](window.WindowManager.md).[setMinSize](window.WindowManager.md#setminsize)

#### Defined in

[window.ts:841](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L841)

___

### setPosition

▸ **setPosition**(`position`): `Promise`<`void`\>

Sets the window outer position.

**`example`**
```typescript
import { appWindow, LogicalPosition } from '@tauri-apps/api/window'
await appWindow.setPosition(new LogicalPosition(600, 500))
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `position` | [`PhysicalPosition`](window.PhysicalPosition.md) \| [`LogicalPosition`](window.LogicalPosition.md) | The new position, in logical or physical pixels. |

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Inherited from

[WindowManager](window.WindowManager.md).[setPosition](window.WindowManager.md#setposition)

#### Defined in

[window.ts:925](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L925)

___

### setResizable

▸ **setResizable**(`resizable`): `Promise`<`void`\>

Updates the window resizable flag.

#### Parameters

| Name | Type |
| :------ | :------ |
| `resizable` | `boolean` |

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Inherited from

[WindowManager](window.WindowManager.md).[setResizable](window.WindowManager.md#setresizable)

#### Defined in

[window.ts:550](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L550)

___

### setSize

▸ **setSize**(`size`): `Promise`<`void`\>

Resizes the window with a new inner size.

**`example`**
```typescript
import { appWindow, LogicalSize } from '@tauri-apps/api/window'
await appWindow.setSize(new LogicalSize(600, 500))
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `size` | [`PhysicalSize`](window.PhysicalSize.md) \| [`LogicalSize`](window.LogicalSize.md) | The logical or physical inner size. |

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Inherited from

[WindowManager](window.WindowManager.md).[setSize](window.WindowManager.md#setsize)

#### Defined in

[window.ts:803](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L803)

___

### setSkipTaskbar

▸ **setSkipTaskbar**(`skip`): `Promise`<`void`\>

Whether to show the window icon in the task bar or not.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `skip` | `boolean` | true to hide window icon, false to show it. |

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Inherited from

[WindowManager](window.WindowManager.md).[setSkipTaskbar](window.WindowManager.md#setskiptaskbar)

#### Defined in

[window.ts:1030](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L1030)

___

### setTitle

▸ **setTitle**(`title`): `Promise`<`void`\>

Sets the window title.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `title` | `string` | The new title |

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Inherited from

[WindowManager](window.WindowManager.md).[setTitle](window.WindowManager.md#settitle)

#### Defined in

[window.ts:572](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L572)

___

### show

▸ **show**(): `Promise`<`void`\>

Sets the window visibility to true.

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Inherited from

[WindowManager](window.WindowManager.md).[show](window.WindowManager.md#show)

#### Defined in

[window.ts:693](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L693)

___

### startDragging

▸ **startDragging**(): `Promise`<`void`\>

Starts dragging the window.

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Inherited from

[WindowManager](window.WindowManager.md).[startDragging](window.WindowManager.md#startdragging)

#### Defined in

[window.ts:1051](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L1051)

___

### toggleMaximize

▸ **toggleMaximize**(): `Promise`<`void`\>

Toggles the window maximized state.

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Inherited from

[WindowManager](window.WindowManager.md).[toggleMaximize](window.WindowManager.md#togglemaximize)

#### Defined in

[window.ts:633](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L633)

___

### unmaximize

▸ **unmaximize**(): `Promise`<`void`\>

Unmaximizes the window.

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Inherited from

[WindowManager](window.WindowManager.md).[unmaximize](window.WindowManager.md#unmaximize)

#### Defined in

[window.ts:613](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L613)

___

### unminimize

▸ **unminimize**(): `Promise`<`void`\>

Unminimizes the window.

#### Returns

`Promise`<`void`\>

A promise indicating the success or failure of the operation.

#### Inherited from

[WindowManager](window.WindowManager.md).[unminimize](window.WindowManager.md#unminimize)

#### Defined in

[window.ts:673](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L673)

___

### getByLabel

▸ `Static` **getByLabel**(`label`): ``null`` \| [`WebviewWindow`](window.WebviewWindow.md)

Gets the WebviewWindow for the webview associated with the given label.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `label` | `string` | The webview window label. |

#### Returns

``null`` \| [`WebviewWindow`](window.WebviewWindow.md)

The WebviewWindow instance to communicate with the webview or null if the webview doesn't exist.

#### Defined in

[window.ts:1127](https://github.com/tauri-apps/tauri/blob/d5400a3/tooling/api/src/window.ts#L1127)
