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

Go to https://www.mono-project.com/download/stable/#download-lin-debian for guide.  See the EXAMPLES page for some great example code.

```bash
sudo apt install dirmngr ca-certificates gnupg
sudo gpg --homedir /tmp --no-default-keyring --keyring /usr/share/keyrings/mono-official-archive-keyring.gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF
echo "deb [signed-by=/usr/share/keyrings/mono-official-archive-keyring.gpg] https://download.mono-project.com/repo/debian stable-buster main" | sudo tee /etc/apt/sources.list.d/mono-official-stable.list
sudo apt update

sudo apt install mono-complete

# Test https is working - this should not error
csharp -e 'new System.Net.WebClient ().DownloadString ("https://www.nuget.org")'

# This should do exactly as it says
csharp -e 'for (int i = 0; i < 10; i++) {Console.WriteLine(i);}'
```
