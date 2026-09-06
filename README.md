## Disclaimer (part I added for this repo)

Wanted to experiment with some Flatpak apps on my MuseBook but while the freedesktop-sdk seems to be built for risc-v, I could not find any actual repo for it. Maybe I am stoopid but just in case someone else gets the same idea, I figured, it might be a good idea to upload it somewhere publicly accessible.

### How to download/install
First of all this is not optimal but because of the file size limits I figured this might still be the best way without linking an external page for downloading.
- Download each of the 3 parts for the desired release on the release page
- Put them back together like this (change the version number in case this is outdated):
```
cat flatpak-repo-riscv64-25.08.16.part.* > flatpak-repo-riscv64-25.08.16.tar.gz
```
- Then untar the archive:
```
tar -zxvf flatpak-repo-riscv64-25.08.16.tar.gz
```
- Add the repo locally like this:
```
flatpak remote-add --user --no-gpg-verify freedesktop-local repo
```
- Install the runtime and/or sdk:
```
flatpak install --user freedesktop-local org.freedesktop.Platform org.freedesktop.Sdk
```

# Welcome to Freedesktop SDK (official Part)

[Freedesktop SDK](https://freedesktop-sdk.io/) is a free, community-developed, and open-source project with a number of components that help you simplify the process of creating different software artifacts. More common use cases include building containers, Flatpak runtimes, or complete operating systems.

The Freedesktop SDK project is not an endorsement of a particular platform or selection of technologies by the Freedesktop organization.
The SDK aims to support a common interoperable platform for projects such as GNOME, KDE, and Flatpak by providing integration and validation of a shared set of dependencies.

## Documentation

Visit the [Freedesktop SDK documentation portal](https://freedesktop-sdk.gitlab.io/documentation/) to find out more about the project and its use cases:

- [Getting started](https://freedesktop-sdk.gitlab.io/documentation/getting-started/)
- [Using the SDK](https://freedesktop-sdk.gitlab.io/documentation/guides/using-the-sdk/)
- [Contributing to the SDK](https://freedesktop-sdk.gitlab.io/documentation/getting-started/contributing/)
- [Troubleshooting](https://freedesktop-sdk.gitlab.io/documentation/reference/troubleshooting/)

## Acknowledgements

This project wouldn't be possible without the work of a few individuals and
groups, and we would like to take a moment to thank them:

- Alex Larsson, who not only gave us [Flatpak](https://flatpak.org) but also the original [Freedesktop SDK](https://github.com/flatpak/freedesktop-sdk-images) (versions 1.2 to 1.6).
- The wider Flatpak community, of which we are only a small part, and who constantly help us.
- The [BuildStream](https://buildstream.build/) community, who gave the world this amazing tool that makes building and maintaining our project so easy and fun.
- Dodji Seketeli, who wrote [libabigail](https://sourceware.org/libabigail/), which allows us to ensure we do not break apps, and tirelessly works with us on fixing any bug we encounter.
- [Codethink](https://www.codethink.co.uk/), for assigning some of their engineers' time to this project.
- [OSU Open Source Lab](https://osuosl.org/) for the x86 runners.
- [Equinix (formerly packet)](https://www.equinix.com/) for the aarch64 runners.
