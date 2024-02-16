
# appStorage - puppeteerApp
**Kind**: global class

缓存数据，类似于 localStorage，但是是应用级别的存储，不会因为清除缓存而被清除。

## appStorage.setItem(key, value)
设置存储项
Sets an item in the application storage with the given key and value.
If the value is null, the item will be removed.

**Kind**: static method of [<code>appStorage</code>](#appStorage)

| Param | Type | Description |
| --- | --- | --- |
| key | <code>string</code> | The key of the item to set or remove. |
| value | <code>\*</code> | The value of the item to set. If null, the item will be removed. |

<a name="appStorage.getItem"></a>

## appStorage.getItem(key) ⇒ <code>string</code>
获取存储项
Retrieves an item from the application storage with the given key.

**Kind**: static method of [<code>appStorage</code>](#appStorage)
**Returns**: <code>string</code> - - The value of the item associated with the key, or null if the key does not exist.

| Param | Type | Description |
| --- | --- | --- |
| key | <code>string</code> | The key of the item to retrieve. |

<a name="appStorage.removeItem"></a>

## appStorage.removeItem(key)
删除存储项
Removes an item from the application storage with the given key.

**Kind**: static method of [<code>appStorage</code>](#appStorage)

| Param | Type | Description |
| --- | --- | --- |
| key | <code>string</code> | The key of the item to remove. |

<a name="appStorage.clear"></a>

## appStorage.clear()
清空存储
Clears all items from the application storage.

**Kind**: static method of [<code>appStorage</code>](#appStorage)