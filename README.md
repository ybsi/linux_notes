# linux_notes

## Switching to dvorak layout (Debian)
https://powertyping.com/switch.html
`setxkbmap dvorak`

## Zipping

```bash
tar -xzvf yourfile.tar.gz -C /path/to/destination
```

## Installing dotnet (specifically 7.0)

Go to https://learn.microsoft.com/en-us/dotnet/core/install/linux-scripted-manual for guide.

```bash
# Install dependencies
sudo apt install libc6 libgcc1 libgssapi-krb5-2 libicu67 libssl1.1 libstdc++6 zlib1g

# This is the 'scripted' install method.
wget https://dot.net/v1/dotnet-install.sh -O dotnet-install.sh
chmod +x ./dotnet-install.sh
./dotnet-install.sh --channel 7.0

dotnet-install: Attempting to download using aka.ms link https://dotnetcli.azureedge.net/dotnet/Sdk/7.0.404/dotnet-sdk-7.0.404-linux-x64.tar.gz
dotnet-install: Remote file https://dotnetcli.azureedge.net/dotnet/Sdk/7.0.404/dotnet-sdk-7.0.404-linux-x64.tar.gz size is 219088775 bytes.
dotnet-install: Extracting zip from https://dotnetcli.azureedge.net/dotnet/Sdk/7.0.404/dotnet-sdk-7.0.404-linux-x64.tar.gz
dotnet-install: Downloaded file size is 219088775 bytes.
dotnet-install: The remote and local file sizes are equal.
dotnet-install: Installed version is 7.0.404
dotnet-install: Adding to current process PATH: `/home/cameronb/.dotnet`. Note: This change will be visible only when sourcing script.
dotnet-install: Note that the script does not resolve dependencies during installation.
dotnet-install: To check the list of dependencies, go to https://learn.microsoft.com/dotnet/core/install, select your operating system and check the "Dependencies" section.
dotnet-install: Installation finished successfully.

# Set environment variables
export DOTNET_ROOT=$HOME/.dotnet
export PATH=$PATH:$DOTNET_ROOT:$DOTNET_ROOT/tools
```

## Installing Mono

```bash

```
