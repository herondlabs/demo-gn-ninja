# demo-gn-ninja
# run this repo on Linux environment or Windows

# Linux set up
- Grab gn binary for linux at: https://gn.googlesource.com/gn/
- Grab ninja binary for linux at: https://github.com/ninja-build/ninja/releases

# Windows setup 
1. Install [LLVM-16.0.0-win64.exe](https://github.com/llvm/llvm-project/releases/download/llvmorg-16.0.0/LLVM-16.0.0-win64.exe) for windows
1. Add path to the bin folder of LLVM to Path under System variables (in my case it is: C:\Program Files\LLVM\bin)
1. Download gn binary: https://chrome-infra-packages.appspot.com/dl/gn/gn/windows-amd64/+/latest
2. Download ninja binary: https://github.com/ninja-build/ninja/releases

## Usage (assuming all of these commands is run at the root of the project - location where .gn file located)
### Gn gen
- gn gen out/test1
- gn gen out/test3 --args="is_two_people = false"
- On windows, If you haven't added gn or ninja binary to environment variables, you have to manually run:
`[path_to_gn_binary_folder] gen out/test1`
- In my case for example: `C:\Users\cuongnq\Downloads\gn-windows-amd64\gn.exe gn gen out\test1`

### Build
ninja –C [gen_folder] [target name]
ex: ninja -C out/test1 ​all

### Find dependency of a target
gn desc [gen_folder] [target_name]
ex: gn desc out/test1 //helloservice:hello2

### Find which target reference on specific target
gn refs [gen_folder] [target_name]
ex: gn refs out/test1 //helloservice:hello2
