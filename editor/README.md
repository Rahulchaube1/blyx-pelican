# Blyx Pelican

Compare per-request aligned I/O with coalesced unaligned reads for a sorted trace.

This extension includes the Blyx Pelican 0.1.0 source, a runnable example and completions for its public functions. It uses the Blyx Language extension for syntax highlighting and execution.

## Run in the editor

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

## Use Pelican in a project

Extract the starter into a new folder. It contains `main.blyx`, the licensed framework source in `vendor/pelican`, and a VS Code task. With the Blyx 0.2.1 compiler and host toolchain installed, run `blyxc native-run main.blyx` from that folder. Type `blyx-pelican-` in a Blyx file to see the framework completions. [Download the starter ZIP](https://github.com/Rahulchaube1/blyxxxx/releases/download/framework-editors-v0.1.0/blyx-pelican-starter-0.1.0.zip)

[API and input requirements](https://www.blyx-lang.space/packages/pelican) · [Framework source](https://github.com/Rahulchaube1/blyx-pelican/tree/0e96f76439d52d5e74ad2785879ac40d4cde32eb) · [Report an issue](https://github.com/Rahulchaube1/blyx-pelican/issues)

[GitHub Sponsors](https://github.com/sponsors/Rahulchaube1) · [Buy Me a Coffee](https://buymeacoffee.com/rahulchaube)
