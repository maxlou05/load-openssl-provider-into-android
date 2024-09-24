## Aim

Load an openssl provider such as [liboqs-provider](https://github.com/open-quantum-safe/oqs-provider/tree/main) into an [Android app which is running openVPN](https://github.com/schwabe/ics-openvpn),
with the goal of utilizing the new post-quantum ciphers in an Android version of openVPN.

This can be done fairly easily on desktop, by loading a provider (dynamic library) through changing the openssl.cnf after . However, this can be quite tricky in mobile applications.

## Issues

### Loading dynamic libraries from other libraries

Not tested, but doesn't seem to be possible.

### Building static libraries for Android

It is difficult to get all the build files from these many different projects and string them together.
Did not succeed to link the libraries together when attmepting to build from source. There seems to be a little bit of a dependency cycle between lib-oqs

### Openssl config file

This file is located in the app source code, and cannot be changed easily once the application has been packaged. The keys and certificates must be hard-coded into the file (source code) beforehand.
