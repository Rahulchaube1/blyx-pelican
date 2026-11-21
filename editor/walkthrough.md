## Compare merged reads with aligned per-request reads

Returns [independent aligned bytes, coalesced read count, coalesced bytes, bridge-gap bytes]. Values describe two explicitly defined read strategies. Invalid arguments and nonfinite results return an empty vector.

1. Open an empty file named `pelican-demo.blyx`.
2. Type `blyx-pelican-demo` and select **Pelican — runnable example**. You can also use **Snippets: Fill File with Snippet**.
3. Choose **Blyx: Run File** from the command palette. Change an argument near the end of `fn main()` to try another input.

Expected output

```text
24
2
10
1
```

[Work through the example in the browser](https://www.blyx-lang.space/play?example=package-pelican)
