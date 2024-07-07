Reference: [https://dotnetos.org/blog/2022-03-28-dictionary-implementation/](https://dotnetos.org/blog/2022-03-28-dictionary-implementation/ "https://dotnetos.org/blog/2022-03-28-dictionary-implementation/") ![[Pasted image 20240707160854.png]]

## Implementation

The most important implementation elements of the `Dictionary<TKey, TValue>`:

- `buckets` - set of elements with similar hashes
- `entries` - elements of the `Dictionary<TKey, TValue>`
- `freeList` - index of the first free place
- `freeCount` - the number of empty spaces in the array, not at the end
- `count` - the number of elements that are currently in the `Dictionary<TKey, TValue>`
- `version` - changes as the `Dictionary<TKey, TValue>` is modified

…and a few more equally important elements that `Entry` contains:

- `_key` - key to identify element with `TKey` type
- `_value` - value of an element with `TValue` type
- `_hashCode` - numeric value used to identify an object in hash-based collection
- `_next` - describes the next item in the `bucket`