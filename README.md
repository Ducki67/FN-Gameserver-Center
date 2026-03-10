# Collected-FN-Game-Servers (🚧 Soon update!!)
Collected FN Game Servers from other archives and sources. Open-source, free to use!

I'll list features in more detail soon — see the Features.md for current notes:
[Features](https://github.com/Ducki67/FN-Gameserver-Center/blob/main/Features.md)

---

## Suggesting Game-Servers
If you'd like to suggest a gameserver:
- Open a new issue in this repository.
- Attach the gameserver source (or a link to it) and any notes about version, branch, or build instructions.
- I may test it and, if appropriate, add it to this collection.

---

## Clarification ❗
A few quick notes about this repo:
1. This repo is intended to collect publicly available, open-source gameserver source code. It is not for leaking private or proprietary code.
2. I will NOT provide source code for Chapters beyond C3S4 (no Chapter 4/5 gameserver sources here).
3. All listed gameservers are open-source, known, and publicly published.

---

## Thanks
Special thanks for 27 stars on this repo — really appreciate the support! ❤️

---

## Requirements
- Visual Studio 2022 (or a compatible version; VS2026 if you have it)
- A gameserver source from the list in this repo
- Basic knowledge of C++ and debugging/building native projects
- Windows x64 development tools and SDKs installed

---

## Building the DLL — Step-by-step

Below are clear, repeatable steps for building a gameserver DLL from source.

### 1) Open the project
- Open the solution (`.sln`) or project (`.vcxproj`) in Visual Studio.
- In Solution Explorer expand the solution/project to view files and folders.

### 2) Update configuration values
- Look for configuration files such as:
  - `Config.h`, `Configuration.h`, `Globals.h`
  - `Settings.h`, `Options.h`
  - Files named `*.config`, `*.ini`, or any `namespace Globals|Config|Configuration`
- If you don't immediately see a config file, use Visual Studio's search (Ctrl+F) and search for:
  - `Globals`, `Configuration`, `Config`, or class/struct names like `struct Config`
- Update the necessary values (paths, ports, hostnames, build flags, etc.) so the project builds and links on your machine.

Example search tips:
```
Ctrl+F → search for: Globals
Solution-wide search (Ctrl+Shift+F) → names: Configuration, Config, Globals
```

### 3) Set build configuration and platform
- At the top of Visual Studio:
  - Set the Configuration to `Release` (or `Debug` while testing).
  - Set the Platform to `x64`.
  - Some projects may provide a `Client` configuration — pick the one appropriate for the DLL you want to build.

### 4) Build in Visual Studio (GUI)
- Build → Build Solution, or press `Ctrl+Shift+B`.
- Watch the Output window for errors and warnings.

### 5) (Optional) Build from the command line
If you prefer a CLI build (useful for automation or CI):
- Open "Developer Command Prompt for VS".
- Run:
```
msbuild path\to\YourSolution.sln /p:Configuration=Release /p:Platform=x64
```
- Or use `devenv`:
```
devenv path\to\YourSolution.sln /Build "Release|x64"
```

### 6) Locate the built DLL
- Typical output folder:
```
<project_folder>\x64\Release\YourGameserver.dll
```
- Some projects use `bin\Release`, `output\Release`, or other custom folders — check the project's `Output Directory` setting in Project Properties → General.

---

## Post-build: quick checks
- Confirm the DLL file exists in the expected output folder.
- If the project requires additional runtime files (config, data files, third-party DLLs), copy them alongside your built DLL.
- If you need to test hooking or injecting the DLL into a client, ensure you follow the client's rules and legal/ethical guidelines.

---

## Troubleshooting — common issues
- Missing includes or headers:
  - Ensure Windows SDK and necessary third-party SDKs/libraries are installed and their include/lib paths are configured in Project Properties.
- Linker errors (unresolved externals):
  - Verify required .lib files are linked and the correct calling conventions/macros are used.
- CRT mismatch or runtime errors:
  - Make sure runtime library settings match across projects (Project Properties → C/C++ → Code Generation → Runtime Library).
- 32-bit vs 64-bit:
  - Building for `x86` when you need `x64` (or vice versa) will cause runtime failures — confirm platform.
- If build fails with many errors, try `Clean Solution` then `Rebuild Solution`.

If you hit a specific error, open an issue with the build log or paste the relevant error messages — I can help diagnose further.

---

## Tips
- Keep a copy of the original project settings before making large changes.
- Use a virtual machine or isolated environment if you're testing code that interacts with game clients.
- Document any manual changes you make to a game's configuration so they can be reproduced.
