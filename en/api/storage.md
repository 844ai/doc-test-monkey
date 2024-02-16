
# appStorage - puppeteerApp
**Kind**: global class

The cache data, similar to localStorage, but it is application-level storage and will not be cleared when clearing the cache.

## appStorage.setItem(key, value)
Set the storage item
Sets an item in the application storage with the given key and value.
If the value is null, the item will be removed.

**Kind**: static method of [<code>appStorage</code>](#appStorage)

| Param | Type | Description |
| --- | --- | --- |
| key | <code>string</code> | The key of the item to set or remove. |
| value | <code>\*</code> | The value of the item to set. If null, the item will be removed. |

<a name="appStorage.getItem"></a>

## appStorage.getItem(key) ⇒ <code>string</code>
Get the storage item.
Retrieves an item from the application storage with the given key.

**Kind**: static method of [<code>appStorage</code>](#appStorage)
**Returns**: <code>string</code> - - The value of the item associated with the key, or null if the key does not exist.

| Param | Type | Description |
| --- | --- | --- |
| key | <code>string</code> | The key of the item to retrieve. |

<a name="appStorage.removeItem"></a>

## appStorage.removeItem(key)
remove the storage item
Removes an item from the application storage with the given key.

**Kind**: static method of [<code>appStorage</code>](#appStorage)

| Param | Type | Description |
| --- | --- | --- |
| key | <code>string</code> | The key of the item to remove. |

<a name="appStorage.clear"></a>

## appStorage.clear()
Clear the storage 
Clears all items from the application storage.

**Kind**: static method of [<code>appStorage</code>](#appStorage)
