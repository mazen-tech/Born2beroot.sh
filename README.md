<p align="center">
  <img src="https://github.com/jotavare/jotavare/blob/main/42/banners/piscine_and_common_core/github_piscine_and_common_core_banner_born2beroot.png">
</p>

<p align="center">
	<img src="https://img.shields.io/badge/status-finished-success?color=%2312bab9&style=flat-square"/>
	<img src="https://img.shields.io/badge/evaluated-21%20%2F%2012%20%2F%202022-success?color=%2312bab9&style=flat-square"/>
	<img src="https://img.shields.io/badge/score-125%20%2F%20100-success?color=%2312bab9&style=flat-square"/>
	<img src="https://img.shields.io/github/languages/top/jotavare/born2beroot?color=%2312bab9&style=flat-square"/>
	<img src="https://img.shields.io/github/last-commit/jotavare/born2beroot?color=%2312bab9&style=flat-square"/>
	<a href='https://www.linkedin.com/in/joaoptoliveira' target="_blank"><img alt='Linkedin' src='https://img.shields.io/badge/LinkedIn-100000?style=flat-square&logo=Linkedin&logoColor=white&labelColor=0A66C2&color=0A66C2'/></a>
	<a href='https://profile.intra.42.fr/users/jotavare' target="_blank"><img alt='42' src='https://img.shields.io/badge/Porto-100000?style=flat-square&logo=42&logoColor=white&labelColor=000000&color=000000'/></a>
</p>

<p align="center">
	<a href="#about">About</a> •
	<a href="#mandatory">Mandatory</a> •
	<a href="#bonus">Bonus</a> •
	<a href="#norminette">Norminette</a> •
	<a href="#license">License</a>
</p>

## ABOUT
This system administration project focuses on setting up a secure virtual machine. It covers key topics such as virtualization, partitioning, LVM, command-line tools, SSH, and system security measures like sudo, firewalls, and password policies. The project repository includes a script for automated tasks and the virtual machine signature.

- [Subject](https://github.com/jotavare/born2beroot/blob/master/subject/en_subject_born2beroot.pdf) `PDF`
- [References](https://github.com/jotavare/42-resources#01-born2beroot) `GitHub`

## MANDATORY
> During the evaluation, I was asked questions about the topics below;
- [x] Choose between two Linux-based operating systems: `Rocky` or `Debian`;
- [x] Create at least 2 encrypted partitions using `LVM`;
- [x] Ensure `SSH services` are running on specific ports;
- [x] Configure a `UFW firewall` and leave only port `4242` open;
- [x] Set up the `hostname` (will be changed during evaluation) and a strong `password policy` for all users;
- [x] Set up a strong `sudo` configuration;
- [x] Create a `monitoring script` that displays specific information every 10 minutes at server startup;

## BONUS
> During the evaluation, also had to justify my choices;
- [x] Set up a different partition structure;
- [x] Set up a functional `WordPress` website with the following services: `lighttpd`, `MariaDB` and `PHP`;
- [x] Set up a service of my own choice that I think is useful (justify that choice);

## commands you need to know
#### uname -a

```bash
is used in Unix-like operating systems (such as Linux) to display system information. When you execute uname -a, it prints out various details about the system, including:

Kernel name
Network node hostname
Kernel release
Kernel version
Machine hardware architecture
Operating system
```

#### grep "physical id" /proc/cpuinfo | wc -l

```bash
This command counts the number of physical CPU IDs listed in the /proc/cpuinfo file and prints the count
```

#### grep "processor" /proc/cpuinfo | wc -l
```bash
This command counts the number of processor entries listed in the /proc/cpuinfo file and prints the count
```

#### free --mega | awk '$1 == "Mem:" {print $2}'
```bash
This command retrieves and prints the total physical memory available in megabytes by filtering the output of the free command using awk
```

#### free --mega | awk '$1 == "Mem:" {print $3}'
```bash
This command retrieves and prints the amount of used physical memory in megabytes by filtering the output of the free command using awk
```

#### vmstat 1 2 | tail -1 | awk '{printf $15}'
```bash
This command prints the value of the 15th column of the output from vmstat 1 2 command after filtering through tail, displaying the second set of statistics
```

#### who -b | awk '$1 == "system" {print $3 " " $4}'
```bash
This command extracts and prints the system boot time by filtering the output of the who -b command using awk, displaying the date and time
```
#### ss -ta | grep ESTAB | wc -l
```bash
This command counts the number of established (ESTAB) connections by filtering the output of ss -ta command using grep, then using wc -l to count the lines
```

#### hostname -I
```bash
The command hostname -I displays the IP addresses associated with the current system's hostname. It prints the IP addresses on a single line, separated by spaces
```

#### ip link | grep "link/ether" | awk '{print $2}'
```bash
This command extracts and prints the MAC addresses of network interfaces by filtering the output of ip link
```

#### journalctl _COMM=sudo | grep COMMAND | wc -l
```bash
This command counts the occurrences of the string "COMMAND" within the logs generated by the sudo command in the systemd journal
```
