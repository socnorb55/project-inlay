# Contributing to project-inlay

Thanks for your interest in project-inlay, a custom macro pad built around custom PCBs and firmware written in Rust.

The project is still in its early stages. The goal is to document the hardware and firmware clearly enough that others can replicate the macro pad as it develops.

## How to Help

You are welcome to:

- Report bugs, design issues, and documentation gaps.
- Suggest improvements or ideas through GitHub issues.
- Share relevant build, flashing, or hardware feedback.

Please do not open pull requests. Changes are developed and integrated by the project owner, but issue reports and thoughtful suggestions are welcome.

## Reporting an Issue

Before opening an issue, check whether a similar issue already exists. When submitting one, choose the appropriate issue template and fill it out completely. Include useful details such as:

- What you expected to happen.
- What happened instead.
- Relevant PCB revision, firmware version, or hardware configuration.
- Reproduction steps, logs, photos, or other supporting information.

## Commit Messages

Commits should follow Semantic Versioning conventions where a version or release is involved:

- **Major:** incompatible hardware, firmware, or interface changes.
- **Minor:** backwards-compatible features or capabilities.
- **Patch:** backwards-compatible fixes and small improvements.

Keep commit messages concise and describe the user-visible or hardware-visible change. As the project gains implementation tooling, this guide will be updated with the exact development and validation commands.

## Replicating the Project

The project is not yet developed, so setup, build, flashing, and testing instructions are not available yet. Once the PCB design and Rust firmware exist, the project will document:

- Required tools and dependencies.
- PCB fabrication and assembly steps.
- Firmware build and flashing commands.
- Supported hardware revisions.
- Validation and troubleshooting steps.

Please use issues to report anything that makes the project difficult to replicate.

## Code of Conduct

Be respectful, specific, and constructive. The aim is to make the macro pad easier to build, understand, and improve.