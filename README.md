# Swift
This repo contains Hikari's Swift Ports. It's ideal for Xcode users to use this fork instead of the main repo since Swift's Clang mimics Apple's Clang's behaviour better than LLVM upstream.
# Building
We will use the branch ``swift-4.1-branch`` as an example. We assume this repo is cloned to ``~/Development/SwiftSRC/``   
When you switch to that branch, you will notice that ``README.md`` says it needs Xcode 9.3. You **must** install the **exact** same version of Xcode or otherwise your build will likely fail.      
Assume your Xcode 9.3 is installed at ``/Applications/Xcode93.app``, open terminal and execute ``sudo xcode-select -switch /Applications/Xcode93.app``    
Then we can start building, ``cd ~/Development/SwiftSRC/ && ./swift/utils/build-toolchain Hikari`` and you are ready to go.   
It takes around 1.5~3 hours to build the toolchain. If everything went well you should be able to find a zipped file under ``~/Development/SwiftSRC/``, this is your toolchain. 

# Things to Note
- Since this is using the exact same Core as the main repo, Obfuscation bugs are not fixed, however this supports Swift and more importantly, Xcode won't bitch about various stuff which should in turn help you build more Xcode projects successfully.
- This forked version's Core is still licensed under the exact same AGPLV3 License as the main repo.
- The Core contains bunch of hacks all over the place, while they shouldn't be an issue when you are compiling LLVM in ``MinSizeRelease``, Swift compiles LLVM with all asserts enabled so these hacks might trigger an assertation. In which case unfortunately I won't be able to help since cherry picking all the fixes from the private version and backport them to here is a giant pain-in-ass.  


Zhang
