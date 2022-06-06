# [NCURSES (New Curses)](http://www.gnu.org/software/ncurses/) Examples

## References

- [The GNU C Reference Manual](https://www.gnu.org/software/gnu-c-manual/gnu-c-manual.pdf)
- [The GNU C Library Reference Manual](https://www.gnu.org/software/libc/manual/pdf/libc.pdf)
- [NCURSES Programming HOWTO](https://tldp.org/HOWTO/html_single/NCURSES-Programming-HOWTO/)

## Requirements

### Windows Requirements

Open [PowerShell](https://docs.microsoft.com/en-us/powershell/scripting/overview) as an administrator and install the [Chocolatey](https://chocolatey.org/) package manager:

```sh
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

Get [GNU Make](https://www.gnu.org/software/make/), [GCC](https://gcc.gnu.org/), [Git](https://git-scm.com/), [CMake](https://cmake.org/), [MSYS2](https://www.msys2.org/), [Ninja](https://ninja-build.org/) and PowerShell Core:

```sh
choco install make mingw git cmake msys2 ninja powershell-core -y
```

Get the [`Vcpkg`](https://devblogs.microsoft.com/cppblog/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/) tool, to get and build C++ open source libraries on Windows:

```sh
git clone --single-branch -b 2022.05.10 https://github.com/Microsoft/vcpkg
.\vcpkg\bootstrap-vcpkg.bat
```

Get NCURSES, and [build the `vcpkg` with `Mingw`](https://vcpkg.io/en/docs/users/mingw.html#mingw-native):

```sh
.\vcpkg\vcpkg search ncurses
# .\vcpkg\vcpkg install ncurses --triplet=x64-windows
.\vcpkg\vcpkg install ncurses --triplet=x64-mingw-static
```

### Linux (Debian and Derivates) Requirements

```sh
sudo apt install libncurses-dev
```

## Build and Run

```
make
cd demo/exe
./hello_world
```
