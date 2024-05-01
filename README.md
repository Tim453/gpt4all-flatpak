# gpt4all-Flatpak

This repo contains a manifest to build a gpt4all flatpak

### Dependencies
To build the flatpak the following SDKs/Runtimes need to be installed:
```
flatpak install flathub io.qt.qtwebengine.BaseApp//6.6
flatpak install flathub org.kde.Platform//6.6
flatpak install flathub org.kde.Sdk//6.6
```


### Buld and install

To build and install run:

```
flatpak-builder --user --install --force-clean build-dir io.gpt4all.gpt4all.yml
```

In flatpak-builder version <= 1.2.2 is a [Bug](https://github.com/flatpak/flatpak-builder/issues/495) , that leads to an error while checking out git submodules. A quick (but vulnerable) solution:
```
git config --global protocol.file.allow always
```
