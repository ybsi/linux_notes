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
```

## Installing Mono

```bash

```
