# Cybersecurity Testing Lab Setup - README

Yeh README document "WK1-PM1 - Week1 - Project Module1 - Lab Setup Virtualbox and Kali Linux v4.2.pdf" ke aadhar par cybersecurity lab setup karne ki jankari deta hai.

## Lab Architecture aur Requirements
* **Host System**: Windows 10 machine jisme kam se kam 8GB RAM, 256GB SSD, aur Core i3/i5 processor (ya saman) ho[cite: 2].
* **Virtualization**: VirtualBox ka latest recommended version[cite: 1].
* **Attacking Machine**: Kali Linux[cite: 1].

## Network Configuration
* **Network Type**: Custom NATNetwork set karein[cite: 2].
* **Subnet**: 10.0.0.0/24 jisme DHCP enabled ho[cite: 1, 4].
* **Kali Linux IP**: Manual IP 10.0.0.2/24 aur gateway 10.0.0.1 set karein[cite: 1, 6].
* **DNS Settings**: 8.8.8.8 set karein (internet issue aane par 10.0.0.1 ka upyog karein)[cite: 6].
* **Internet Access**: Kali Linux VM mein full internet access anivarya hai[cite: 1].

## Kali Linux Virtual Machine Settings
* **RAM**: Base memory ko 2048 MB par set karein[cite: 8].
* **User Interface**: VM settings mein clipboard sharing aur file drag/drop feature ko enable karein[cite: 1].
* **Shared Folders**: Host machine se `/downloads` folder share karne ke liye Shared Folders enable karein[cite: 1].

## Phase 1: Base Installation Steps
1. 7-zip software download karke install karein[cite: 3].
2. Apne host PC par VirtualBox download aur install karein[cite: 3].
3. VirtualBox mein network settings configure karein aur 10.0.0.0/24 subnet ka NATNetwork banayein[cite: 3, 4].
4. Kali Linux Virtual Machine ki file download karein aur use VirtualBox mein import karein[cite: 3].
5. Kali Linux VM open karke uski IP configuration setup karein[cite: 3, 6].
6. Pura setup hone ke baad Kali Linux VM ka snapshot save karein[cite: 3].

## Troubleshooting: Network Connectivity Issues
Yadi Kali VM mein internet access nahi hai (jo ki VirtualBox v7 ya Kali 2026.1+ mein common hai), toh yeh commands terminal mein run karein aur VM restart karein[cite: 7]:
* `sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0`[cite: 7]
* `sudo nmcli connection down "Wired connection 1"`[cite: 7]
* `sudo nmcli connection up "Wired connection 1"`[cite: 7]

## Phase 2: Optional Target Machines
Bhavishya ke practical tasks ke liye, aap is NATNetwork par niche diye gaye machines install kar sakte hain, unka aapas mein ping test kar sakte hain aur snapshot le sakte hain[cite: 3]:
* **Windows 11**: IP Address 10.0.0.16/24[cite: 2].
* **Windows 10**: IP Address 10.0.0.10/24[cite: 2].
* **Windows 7**: IP Address 10.0.0.7/24[cite: 2].
* **Android**: IP Address 10.0.0.9/24, iske display settings mein VBoxVGA graphics controller select karein aur 3D Acceleration ko untick (disable) rakhein[cite: 2, 10].
