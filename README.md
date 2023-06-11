# gpt4all-Flatpak

This repo contains a manifest to build a gpt4all flatpak

### Dependencies
To build the flatpak the following SDKs/Runtimes need to be installed:
```
flatpak install org.freedesktop.Sdk.Extension.node14//22.08
flatpak install org.kde.Platform//6.5
```

In flatpak-builder version <= 1.2.2 is a [Bug](https://github.com/flatpak/flatpak-builder/issues/495) , that leads to an error while checking out git submodules. Here is a quick (but vulnerable) solution:
```
git config --global protocol.file.allow always
```

### Buld and install

To build and install run:

```
flatpak-builder --install --force-clean build-dir com.github.gpt4all.yml
```