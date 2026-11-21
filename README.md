<img src="assets/logo.png" width="112" height="112" alt="A brown pelican opens its ochre throat pouch beneath a long bill.">

# Pelican

Compare per-request aligned I/O with coalesced unaligned reads for a sorted trace. This Blyx workflow framework is part of the collections and storage collection.

Merging requests saves seeks but can read unused gap bytes. Report each cost explicitly before changing a storage access pattern. [POSIX, pread and pwrite offsets](https://pubs.opengroup.org/onlinepubs/9799919799/functions/pread.html)

## Editor extension

Install **RahulChaube.blyx-pelican** to run the worked example and use the framework’s function completions in a Blyx file. Open an empty `.blyx` file, enter `blyx-pelican-demo`, then choose **Blyx: Run File**. [Editor downloads](https://www.blyx-lang.space/packages/pelican#editor) · [Download the extension](https://github.com/Rahulchaube1/blyxxxx/releases/download/framework-editors-v0.1.0/blyx-pelican-0.1.0.vsix) · [Starter with framework source](https://github.com/Rahulchaube1/blyxxxx/releases/download/framework-editors-v0.1.0/blyx-pelican-starter-0.1.0.zip)

## Install and run

Install [Blyx 0.2.1](https://www.blyx-lang.space/download) with a Rust toolchain and host linker for native builds.

```sh
git clone --depth 1 --branch v0.1.0 https://github.com/Rahulchaube1/blyx-pelican.git
cd blyx-pelican
blyxc native-run example.blyx
blyxc native-run tests.blyx
```

[Run the editable browser example](https://www.blyx-lang.space/play?example=package-pelican) · [Package page](https://www.blyx-lang.space/packages/pelican) · [Handbook](https://doc.blyx-lang.space/guide/pelican)

## Import the module

Run this in the directory containing your application's entry file.

```sh
git clone --depth 1 --branch v0.1.0 https://github.com/Rahulchaube1/blyx-pelican.git vendor/pelican
```

```blyx
use vendor::pelican::pelican;

fn main() {
    let starts = [0, 5, 20];
    let lengths = [4, 3, 2];
    let gap = 1.0;
    let block = 8.0;
    let result = pelican_reads(starts, lengths, gap, block);
    if len(result) == 0 { println!("invalid"); return; }
    let mut i = 0;
    while i < len(result) {
        println!(at(result, i));
        i += 1;
    }
}
```

Expected output

```text
24
2
10
1
```

## API

`pelican_reads(starts, lengths, gap, block)`

Returns [independent aligned bytes, coalesced read count, coalesced bytes, bridge-gap bytes]. Values describe two explicitly defined read strategies. Invalid arguments and nonfinite results return an empty vector. Integers carried in numeric vectors use the exact range from −(2^53−1) to 2^53−1.

| Argument | Domain |
| --- | --- |
| starts | Vector of values, each a nonnegative exact integer |
| lengths | Vector of values, each a positive exact integer |
| gap | A nonnegative exact integer |
| block | A positive exact integer |

## Run the command-line project

Run the example with your own numbers. Vector arguments accept up to 16 comma-separated entries; use `[]` for an empty vector. The imported API accepts longer vectors. Invalid arguments return a nonzero exit status.

```sh
blyxc native-run project.blyx -- "0,5,20" "4,3,2" 1 8
```

## Libraries

- [BlockSpan](https://github.com/Rahulchaube1/blyx-blockspan/tree/v0.1.0) — Expand a byte request to whole storage blocks.
- [CoalesceIO](https://github.com/Rahulchaube1/blyx-coalesceio/tree/v0.1.0) — Count merged reads and extra gap bytes for sorted byte requests.

This release includes identical copies of both library modules so a tagged clone can build offline.

## Verification and contributions

The regression suite in [tests.blyx](tests.blyx) checks the example, boundary cases and invalid inputs. Include a short reproducer and your compiler version in [an issue](https://github.com/Rahulchaube1/blyx-pelican/issues). The source is dual-licensed under [MIT](LICENSE-MIT) or [Apache-2.0](LICENSE-APACHE). The [artwork notice](assets/NOTICE.txt) records credits for earlier editions.

## Connect with Rahul Chaube

[Portfolio](https://www.rahulchaube1.com/) · [GitHub](https://github.com/Rahulchaube1) · [LinkedIn](https://www.linkedin.com/in/rahulchaube1) · [Hugging Face](https://huggingface.co/oncody) · [X](https://x.com/RahulChaube_) · [EverestQ](https://www.everestqai.com/) · [Contact](https://www.rahulchaube1.com/contact)

[Blyx website](https://www.blyx-lang.space/) · [BlyxTorch](https://www.blyx-lang.space/packages/blyxtorch) · [Handbook](https://doc.blyx-lang.space/) · [Community](https://www.blyx-lang.space/community)

Support Rahul’s open-source work through [GitHub Sponsors](https://github.com/sponsors/Rahulchaube1) or [Buy Me a Coffee](https://buymeacoffee.com/rahulchaube).
