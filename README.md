## OpenSSL for iOS, visionOS, macOS (Intel & Apple Silicon M1) & Catalyst - arm64 / x86_64 
depend on ios12

Use the appropriate tag or branch to choose a version.

This repository provides a universal script for building static OpenSSL libraries for use in iOS, visionOS, and macOS & Catalyst applications.
The actual library version is taken from https://github.com/openssl/openssl with an appropriate tag like 'OpenSSL_1_1_1w' or 'openssl-3.2.1'

## Prerequisites
  1) Xcode must be installed because xcodebuild is used to create xcframeworks
  2) ```xcode-select -p``` must point to Xcode app developer directory (by default e.g. /Applications/Xcode.app/Contents/Developer). If it points to CommandLineTools directory you should execute:
  ```sudo xcode-select --reset``` or ```sudo xcode-select -s /Applications/Xcode.app/Contents/Developer```
  3) For the creation of visionOS related artifacts and their integration into the resulting xcframeworks, XROS.platform and XRSimulator.platform should be available in the folder: /Applications/Xcode.app/Contents/Developer/Platforms
 
## How to build?
 - Manually
```
    # clone the repo
    git clone https://github.com/apotocki/openssl-iosx
    
    # build libraries
    cd openssl-iosx
    scripts/build.sh

    # have fun, the result artifacts will be located in 'frameworks' folder.
```    
 - Use cocoapods. Add the following lines into your project's Podfile:
```
    use_frameworks!
    pod 'openssl-iosx', '~> 0.0.2'
    # or optionally more precisely
    # pod 'openssl-iosx', :git => 'https://github.com/apotocki/openssl-iosx', :tag => '3.2.1.1'
```    
install new dependency:
```
   pod install --verbose
```    
