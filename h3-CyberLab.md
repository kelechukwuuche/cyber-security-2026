







# Debian 13 (Trixie) Installation on UTM

**Date:** 10 November 2026  
**Platform:** Apple MacBook M4  
**Virtualization software:** UTM (QEMU, ARM64 virtualization)

## Objective

Install Debian 13 (Trixie) Linux in a virtual machine for the Linux coursework and verify that the system boots and functions correctly.

## Virtual machine configuration

| Component | Configuration |
|---|---|
| Linux distribution | Debian GNU/Linux 13 (Trixie), release 13.7 |
| Installation image | `debian-13.7.0-arm64-netinst.iso` |
| Architecture | ARM64 (`aarch64`) |
| Virtual machine | UTM / QEMU ARM Virtual Machine |
| Memory | 4 GB |
| CPU | 4 cores |
| Virtual storage | 64 GiB |
| Networking | Shared Network (NAT) |
| Desktop environment | Xfce |
| Remote access | OpenSSH server |

![UTM VM configuration](images/h3-CyberLab/setup.jpg)

*Figure 1. UTM configuration showing the ARM64 VM and Debian installer ISO.*

## Installation procedure

1. **Downloaded the installer:** Obtained the Debian 13 (Trixie) ARM64 network-installation ISO from the [official Debian website](https://www.debian.org/releases/trixie/debian-installer/).
2. **Created the VM:** In UTM, selected **Create a New Virtual Machine → Virtualize → Linux**, attached the ISO, configured 4 GB RAM and 4 CPU cores, and allocated a 64 GiB virtual disk.
3. **Started Debian installation:** Booted the VM from the ISO and selected **Graphical install**.
4. **Configured the system:** Selected English, Finland, an English UTF-8 locale, and an appropriate keyboard layout. Set hostname `debian13` and created a standard user account with `sudo` privileges.
5. **Partitioned the virtual disk:** Chose **Guided – use entire disk** on the 68.7 GB Virtio disk (`vda`, equivalent to 64 GiB). The installer configured an EFI System Partition, an ext4 root partition, and swap.

![Debian disk partition layout](images/h3-CyberLab/partition.jpg)

*Figure 2. Guided partition layout on the virtual disk.*

6. **Configured package repositories:** Selected `deb.debian.org` as the package mirror, left the HTTP proxy empty, and declined the optional package-usage survey.
7. **Selected software:** Enabled **Debian desktop environment**, **Xfce**, **SSH server**, and **standard system utilities**.

![Debian software selection](images/h3-CyberLab/software.jpg)

*Figure 3. Selected software packages and services.*

8. **Completed installation:** After Debian reported success, rebooted the VM. The installer initially reappeared because the ISO was still attached; I stopped the VM, ejected the ISO from UTM's CD/DVD drive, and restarted successfully from the virtual disk.

![Debian installation completed](images/h3-CyberLab/complete.jpg)

*Figure 4. Installation-complete screen.*

## Verification

After logging into the Xfce desktop, I ran:

```bash
cat /etc/os-release
uname -m
sudo systemctl status ssh
```

The results confirmed:

- **OS:** Debian GNU/Linux 13 (Trixie), full release **13.7**
- **Architecture:** `aarch64`
- **SSH:** `active (running)` and `enabled`

![Debian version and SSH verification](images/h3-CyberLab/verify.jpg)

*Figure 5. Terminal verification of Debian version, architecture, and SSH service.*

I also checked package repository connectivity using `sudo apt update`; APT reported that the installed packages were up to date.

## Outcome

**Completed successfully.** Debian 13 (Trixie) runs in a UTM virtual machine on the MacBook M4. The Xfce desktop, ARM64 architecture, and SSH service were verified. A VM backup was also created for future coursework; restoration from the backup has not been tested.

## References

- [Debian 13 (Trixie) documentation](https://www.debian.org/releases/trixie/)
- [UTM documentation](https://docs.getutm.app/)
