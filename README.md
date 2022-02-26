# rpihqcam-ansible

An Ansible playbook for provisioning a Raspberry Pi to display the output of a [Raspberry Pi HQ Camera Module](https://www.raspberrypi.com/products/raspberry-pi-high-quality-camera/) on boot.

# Prerequisites

- A Raspberry Pi (we used a 4GB Raspberry Pi 4 Model B)
- A monitor
- [Ansible](https://www.ansible.com/)

## Instructions

1. Write [Raspberry Pi OS Lite](https://www.raspberrypi.com/software/) to SD card
2. Add an empty file named `ssh` to the root of the boot partition (see [here](https://www.raspberrypi.com/news/a-security-update-for-raspbian-pixel/))
3. Boot the Raspberry Pi and make sure it's connected to a wired network (you don't have to close the dialog windows, they will be closed by the playbook)
4. Set the `ansible_host` variable in `hosts` to the Raspberry Pi's local IP address (e.g. as seen in the bottom right of the "Welcome to Raspberry Pi" startup wizard)
5. Run `ssh pi@[ip-here]` to add the Raspberry Pi to the SSH known hosts
6. Run `ansible-playbook -i hosts setup-role.yml`
7. Reboot the Raspberry Pi
