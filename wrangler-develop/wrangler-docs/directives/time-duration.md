# TimeDuration Parser

The TimeDuration parser allows you to parse and validate time duration values with their units. This is useful when working with time intervals, delays, or any other time-based measurements.

## Syntax

```
parse-as-timeduration <column> [as <alias>]
```

## Arguments

* **column**: The column containing the time duration value to parse
* **alias** (optional): The name for the new column containing the parsed value

## Supported Units

The parser supports the following units:
* ns - Nanoseconds
* us - Microseconds (1000 nanoseconds)
* ms - Milliseconds (1000 microseconds)
* s - Seconds (1000 milliseconds)
* m - Minutes (60 seconds)
* h - Hours (60 minutes)
* d - Days (24 hours)

## Example

```
parse-as-timeduration duration as parsed_duration
```

This will parse values like:
* "1.5h" → 5400000000000 nanoseconds
* "30m" → 1800000000000 nanoseconds
* "100ms" → 100000000 nanoseconds

## Error Handling

If a value cannot be parsed as a valid time duration, it will be treated as an error and can be handled using error handling directives like `send-to-error` or `send-to-error-and-continue`. 