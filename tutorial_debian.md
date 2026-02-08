# Debian Installation Guide

This guide outlines the steps to install Debian, specifically configured for a cluster environment.

## Phase 1: Boot and Localization
1.  **Power on** the machine and press **F10** or **F12** to enter the Boot Menu/BIOS.
2.  Select the **USB boot device**.
3.  Choose **Install** (text-based mode recommended).
4.  **Language:** Select **English**.
5.  **Location:** Select **Other → South America → Brazil** (or your local region).
6.  **Locales:** Select **United States** (en_US.UTF-8).
    * *Note: This is crucial to ensure the system uses a dot (`.`) as the decimal separator, which is standard for scientific applications.*
7.  **Keyboard:** Set the layout to **Brazilian** (or compatible with your hardware).

## Phase 2: Network and User Configuration
8.  Ensure the system has an active internet connection.
9.  **Hostname:** Define the system name (e.g., `test`).
10. **Domain name:** Define the cluster domain (e.g., `tutorial`).
11. **User and Password Setup:**
    * Set the **Root** password.
    * Create a user account:
        * **Full name:** e.g., `tutorial`.
        * **Username:** e.g., `tutorial`.
        * **Password:** Set a strong password.
12. **Time Zone:** Select **São Paulo**.
    * *Critical:* All nodes in the cluster must be synchronized to the same time zone.

## Phase 3: Disk Partitioning
13. **Method:** Choose **Guided – use entire disk with LVM** (Logical Volume Management).
14. Select the target hard drive.
15. **Partition Scheme:** Choose **Separate /home partition**.
16. **Confirm:** Select **[Yes]** to write changes to disk.
17. **Volume Size:** When prompted for the volume group size, keep the default (use **all available space**) and continue.
18. **Format:** Confirm the formatting of partitions (**Yes**).

## Phase 4: Package Manager and Software
19. **Mirror:** Choose the nearest mirror for faster downloads (usually detected automatically based on your location).
20. **Proxy:** Leave blank (skip) unless your network requires one.
21. **Popularity Contest:** Choose **No** (optional).
22. **Software Selection:**
    * Uncheck the desktop environment (GNOME/KDE).
    * Select **only**:
        * [x] **SSH server**
        * [x] **Standard system utilities**

## Phase 5: Bootloader and Finalization
23. **GRUB Bootloader:**
    * Install the GRUB boot loader to the primary drive? **Yes**.
    * **Device:** Select the correct hard drive manually (do **not** select the USB stick).
24. **Finish:** Remove the USB drive and select **Continue** to reboot.

---

## Post-Installation
To shut down the machine safely via the terminal, run:

```bash
systemctl poweroff
