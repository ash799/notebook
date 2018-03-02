## Configurye Tsinghua IPv6 network environment on Macbook
### Abstract
This tutorial will enable you to get your Macbook connected to the oversea IPv6 websites, whose IPv4 addresses are probably blocked by the GFW .
### Prerequisites
* A Macbook connected to the `Tsinghua` or `Tsinghua-5G`Wi-Fi or in specific wired network conditions
* A viable Tsinghua network account
* The MacOS X app `Terminal`
* The MacOS X app `Automator`
### Brief intro to IPv6
Internet Protocol version 6 (abbreviated as IPv6) is the most recent version of Internet Protocol (IP). So far, most of the famous American IT companies have entitled IPv6 address as an alternative access to their websites.
In China, the routers that support IPv6 approaches can be mostly found in universities.
### 0. Validate your Tsinghua campus network account
First, connect to the `Tsinghua` or `Tsinghua-5G` Wi-Fi, then enter [net.tsinghua.edu.cn](net.tsinghua.edu.cn) to sign in.
To ease the procedure, the following steps are all supposed to be taken in the validated Tsinghua Wi-Fi environment.
### 1. Edit your IPv6 hosts file
The computer file `hosts` is an operation system file that maps **hostnames** to **IP addresses**. Users can arbitrarily edit it so that web browser can recognize the domains in the address bar as IP addresses.
First, enter [https://raw.githubusercontent.com/lennylxx/ipv6-hosts/master/hosts](https://raw.githubusercontent.com/lennylxx/ipv6-hosts/master/hosts), to get enough hosts clauses. Just select all and copy them.
The location of your own `hosts` file is `\etc\hosts`. The files in the path `\etc` are protected by the system, which means any approach to amend files in this path wil be denied. The app `Terminal` is indispensable for achieving the root previlege of the computer and modifying the file, though the procedure seems implicit if you are not a proficient `bash` user.

Let's create a replica of the original `\etc\hosts`, just type in a few letters in the app `Terminal`

```bash
$ cp \etc\hosts ~/Desktop/hosts
```

This command copies the orignial hosts file onto your desktop. Now you can open it with the default text editor in your mac and append the content from [https://raw.githubusercontent.com/lennylxx/ipv6-hosts/master/hosts](https://raw.githubusercontent.com/lennylxx/ipv6-hosts/master/hosts) after the end of previous hosts text. After saving the file, you have already get a  hosts file that make sense. Now let's put it back where it can work.

```bash
$ sudo mv \etc\hosts \etc\hosts.backup
$ sudo mv ~\desktop\hosts \etc\hosts
```

The first command makes a backup of the original version of the hosts file; while the second one moves the hosts on your desktop to the `\etc` path so that it can get down to work.

After all these steps, you should restart your computer to make sure the network configuration has been refreshed.

### 2. Obtain your IPv6 address

The Macbook initial IPv6 address is not usable due to some of the Macbook presets. Some command should go into effect to change the network configuration. 

It may sound quite difficult to modify the network settings. Fortunately, a prefect  solution, supplied by [宗泽略](https://www.zhihu.com/people/zong-ze-lue) from [zhihu.com](zhihu.com), is available online. The thorough process is compressed into a smart app available at [https://pan.baidu.com/s/1boEnYhh](https://pan.baidu.com/s/1boEnYhh). 

After downloading the zip file, move the .app file inside the package to the `Application` path of your computer. Then use the MacOS app `Automator` to open `StartIPV6.app`. Edit the content of PASSWORD as your own computer password to grant the app your computer's root privilege.

**Note** : After this configuration, launch this app `StartIPV6.app`each time you want to get access to IPv6 websites.

### 3. Test 

Now you can try to enter [google.com.hk](ipv6.google.com.hk) to test whether your computer has access to IPv6 sites.

**Note** : youtube, google, gmail, and facebook IPv6 sites is accessible. However, twitter is not included in the IPv6 white lists. If you want to view twitter in Tsinghua, please find other feasible methods.



