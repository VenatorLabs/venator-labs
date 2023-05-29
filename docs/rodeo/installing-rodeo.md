# Installing Rodeo

A Rodeo installer is currently available for Debian Linux variants (Ubuntu & Kali) and Microsoft Windows. Rodeo is also available as a Docker container from the GitHub Container Registry. If you have another operating system, you can either build from source or bring your own version of Java to execute Rodeo. The instructions for each system are listed below in detail.

## Linux

The `rodeo` and `rodeo-service` (named `rodeod` on Linux) are packaged together in a single `deb` installation file. The `deb` package includes an OpenJRE installation so that there are no additional installation dependencies. You can install `rodeo` in the following ways:

### apt Installation

```sh
# ensure environment variables are set
. /etc/os-release

# Add the Venator Labs, Inc. cryptographic public key for verification
wget -O- https://venatorlabs.github.io/ppa/venatorlabs.key | sudo apt-key add -

# add the Venator Labs Personal Package Archive (PPA)
sudo add-apt-repository "https://venatorlabs.github.io/ppa/linux/${OS}/${codename}"

# install latest rodeo version (for a specific version use rodeo-#.#.#)
sudo apt-get update && sudo apt-get install rodeo
```

### Manual Installation

1. Download the linux binary package that matches your operating system and processor architecture from the [Downloads](https://venatorlabs.github.io/ppa/linux) page.

2. Install the `.deb` file using `dpkg --install`.

```sh
sudo dpkg --install rodeo_1.0.0-1_amd64.deb
# Note: the installation will configure the Venator Labs PPA to enable updates
```

Both installation methods will install the `rodeo` and `rodeod` binaries. The `rodeod` binary will be installed as a service and will be started automatically as a non-root system user named `rodeod`. This user is created during installation if it doesn't already exist.

To start the `rodeo` shell, execute the following command:

```sh
/opt/bin/rodeo
```

## Windows

The `rodeo` and `rodeo-service` are packaged together in a single `msi` installation file. The `msi` package includes an OpenJRE installation so that there are no additional installation dependencies. You can install `rodeo` in the following ways:

### Winget (Windows Package Manager)

```pwsh
winget install -e --id VenatorLabs.Rodeo
```

### Manual Installation

1. Download the Microsoft Installer [here](https://venatorlabs.github.io/ppa/windows/).

2. Execute `Rodeo-#.#.#.msi` to start the installation wizard to completion.

Both installation methods will install the `rodeo` and `rodeo-service` binaries. Rodeo-service will be started automatically as a Windows service.

To connect and interact with the Rodeo service, open the Rodeo console through the desktop icon, start menu shortcut, or by executing `rodeo.exe` in a terminal window.

## Docker

Rodeo is also available as a Docker container from Docker Hub. This is a Debian Linux based container loaded with both the `rodeo` and `rodeo-service` binaries. The service is started automatically when the container is run. The entrypoint is configured to open the Rodeo shell by default. To use this method of installation, execute the following commands:

```sh
# Download from GitHub Container Registry
docker pull venatorlabs/rodeo:latest

# Run the container as interactive for rodeo cli
docker run -it venatorlabs/rodeo:latest

# add bind-mounts (-v) to pass data files from your local host to the container
# run without (-it) to tail rodeod logs
```

## BYOJ (Bring Your Own Java)

If you have another operating system, you can still use Rodeo but it requires you to manage the Java JRE installation yourself. Rodeo requires **Java 17 JRE** or higher. After you have installed the Java JRE for your operating system, download the cross-platform Rodeo bundle, `Rodeo [Java]`, from the [Releases](https://github.com/VenatorLabs/rodeo/releases) page or see the instructions for how to build from source below.

```sh
# unpack rodeo bundle
tar -xzvf rodeo-0.0.0.tar.gz
```

To run the cross-platform bundle, execute the following commands:

```sh
# run rodeo-service in background (or separate terminal for tailing logs)
./rodeo-0.0.0/bin/rodeo-service >/dev/null &

# open Rodeo shell
./rodeo-0.0.0/bin/rodeo
# Rodeo>
```
