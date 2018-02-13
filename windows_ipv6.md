# Configure Tsinghua IPv6 network environment on PC
### Abstract
This tutorial will enable you to get your PC connected to the oversea IPv6 websites.
### Prerequistes

* A windows PC connected to the `Tsinghua` or `Tsinghua-5G`Wi-Fi or in specific wired network conditions
* A viable Tsinghua network account
* The windows application `notepad`

### Procedure

* Run the `notepad` with Administrator Privilege.
* Use this notepad to open the file `C:\Windows\System32\drivers\etc\hosts` (The easiest way is getting to the specific position in `windows explorer`; then drag the file into the existing `notepad` window)
* Enter  [https://raw.githubusercontent.com/lennylxx/ipv6-hosts/master/hosts](https://raw.githubusercontent.com/lennylxx/ipv6-hosts/master/hosts) and copy all the texts; then append them at end of  the default contents of `hosts`.
* Reboot
* check [google.com](ipv6.google.com.hk) out

**Note** : You can view my tutorial about enable IPv6 on a Macbook to get further interpretations. 