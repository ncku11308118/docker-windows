# dockur/windows

## Usage

To boot Windows:

```sh
docker compose up --detach
```

To shutdown Windows:

```sh
docker compose stop
```

## WSL2

1. Run the Docker Desktop WSL2 distribution
   ```sh
   wsl --distribution docker-desktop
   ```
2. Load the KVM module
   ```sh
   modprobe kvm_amd
   # or
   modprobe kvm_intel
   ```
3. Check KVM availability
   ```sh
   test -c /dev/kvm && echo KVM supported
   ```
4. Edit `/etc/wsl.conf` for automatic loading [on startup](https://learn.microsoft.com/en-us/windows/wsl/wsl-config#boot-settings)
   ```toml
   [boot]
   command = "modprobe kvm_intel"
   ```
5. Exit the shell (Ctrl+D)
