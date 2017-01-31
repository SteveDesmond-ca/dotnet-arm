# dotnet-arm
## Automated builds of .NET Core for Ubuntu 16.04 on ARM

### Running

1. See [here](https://github.com/dotnet/core/blob/master/samples/RaspberryPiInstructions.md) for prerequisites (for all ARM, not just Raspberry Pi)
2. Head over to the [Releases](https://github.com/stevedesmond-ca/dotnet-arm/releases) and follow instructions there

### Building

1. create an x64 Ubuntu 16.04 VM that has your GitHub SSH key
2. clone this repo (`git clone git@github.com:stevedesmond-ca/dotnet-arm`) otherwise obtain the code
3. `cd dotnet-arm` or wherever you put it
4. `./setup` will run everything to configure your environment for building
  - installing prerequisites
  - checking out all components
  - setting up the chroot for cross-compiling
5. `./build` will kick off the build of all components, or you can build them individually
  - `./build-libuv`
  - `./build-coreclr`
  - `./build-corefx`
  - `./build-corehost`
6. `./test` will take the output of the build and test it in the chroot created during setup
  - if you see `Hello World!`, your build was successful!
7. `./reset` will clean build artifacts and other intermediate/temporary files to prep for the next build
8. `./update` will update all the repos to the latest commit on master
