# ByteSize Parser

The ByteSize parser allows you to parse and validate byte size values with their units. This is useful when working with file sizes, memory allocations, or any other byte-based measurements.

## Syntax

```
parse-as-bytesize <column> [as <alias>]
```

## Arguments

* **column**: The column containing the byte size value to parse
* **alias** (optional): The name for the new column containing the parsed value

## Supported Units

The parser supports the following units:
* B - Bytes
* KB - Kilobytes (1024 bytes)
* MB - Megabytes (1024 KB)
* GB - Gigabytes (1024 MB)
* TB - Terabytes (1024 GB)
* PB - Petabytes (1024 TB)

## Example

```
parse-as-bytesize size as parsed_size
```

This will parse values like:
* "1.5MB" → 1572864 bytes
* "2GB" → 2147483648 bytes
* "500B" → 500 bytes

## Error Handling

If a value cannot be parsed as a valid byte size, it will be treated as an error and can be handled using error handling directives like `send-to-error` or `send-to-error-and-continue`. 