The easiest way to collect these files is to use [bitrise.io's](https://www.bitrise.io) open source [codesigndoc tool](https://github.com/bitrise-tools/codesigndoc). This tool runs a clean Archive on your Mac, and analyzes the Xcode log output to see which code signing files Xcode used during the Archive.

For **Xcode projects** use the following command:

```
bash -l -c "$(curl -sfL https://raw.githubusercontent.com/bitrise-tools/codesigndoc/master/_scripts/install_wrap-xcode.sh)"
```

For **Xamarin project** us the following command:

```
bash -l -c "$(curl -sfL https://raw.githubusercontent.com/bitrise-tools/codesigndoc/master/_scripts/install_wrap-xamarin.sh)"
```

This will archive your project and locate all the required code signing files and provisioning profiles and export it to a directory for you.

!!! warning
    Because `codesigndoc` does a full code archiving and exporting to generate an API, make sure you can build and archive your project. Otherwise it won't be able to locate the files for you

1. Start your Terminal app on your macOS.
2. Run the one liner command above for your project type.
3. The script will download and start itself. It will ask for your Xcode project file. Select the `xcodeproj`, or `xcworkspace` you are using with the Finder app and simply drag and drop it to the Terminal.
![codesigndoc](img/codesigndoc.png)
4. The script will parse your project and show all the available schemes or configurations.
5. Select the one you are using.
6. The `codesigndoc` tool will export all the required code signing files and provisioning profiles for you and open up a Finder window with all of them.

## Exporting using Xcode 8

## Exporting manually
