<!-- cargo-rdme start -->

The `sev-snp-launch` crate provides a Rust-safe implementation of the AMD [SEV
Secure Nested Paging Firmware (SNP)][SEV-SNP] Linux launch APIs.

[SEV-SNP]: https://www.amd.com/content/dam/amd/en/documents/epyc-technical-docs/specifications/56860.pdf

## SEV-SNP Linux APIs

The Linux kernel exposes APIs for managing SEV-SNP enabled KVM virtual machines.
This crate implements Rust-safe APIs for the KVM SEV-SNP launch API provided by
Linux.

## Remarks

Note that the linux kernel provides access to these APIs through a set
of `ioctl`s that are meant to be called on device nodes (`/dev/kvm` and
`/dev/sev`, to be specific). As a result, these `ioctl`s form the substrate
of the `sev-snp-launch` crate. Binaries that result from consumers of this crate
are expected to run as a process with the necessary privileges to interact with
the device nodes.

<!-- cargo-rdme end -->
