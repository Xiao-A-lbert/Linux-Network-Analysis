# Linux Network Analysis

<h2>Description</h2>
In this Linux Network Analysis task, I used netstat, ss, and lsof to show a reverse tcp connection from notmalware.elf.

<h2>Languages and Utilities Used</h2>

- <b>Metasploit</b>
- <b>msfvenom</b>
- <b>Linux CLI</b>

<h2>Environments Used</h2>

- <b>Windows 10 Enterprise</b>
- <b>Ubuntu</b>

<br />
<br />
Creating the malware to attack my Ubuntu vm.

![1) creating notmalware elf](https://github.com/user-attachments/assets/9bb970d4-80dd-4a1f-899d-3b34b7aa58cb)

<br />
<br />
Giving notmalware.elf executable permissions, running it, and confirming a reverse tcp connection.

![2) give x permissio to notmalware, running, completeing connection](https://github.com/user-attachments/assets/03469763-b261-4c34-aaa9-c6a8b21a5db4)

<br />
<br />  
Using "netstat -tnp" to show the PID 3115 of notmalware.elf over port 4444. The command netstat -tnp displays active TCP connections with numerical addresses and port numbers, along with the associated process IDs and program names. Here's a breakdown of the options:
-t: Shows only TCP connections,
-n: Displays numerical addresses and port numbers instead of hostnames and service names,
-p: Shows the PID and name of the program to which each socket belongs.

![3) netstat tnp to show pid](https://github.com/user-attachments/assets/f52ab175-775f-47d0-bfe7-11212ff5f62b)

<br />
<br />
Using "sudo ss -tnp" in a similar but more verbose netstat. Also filtering ss with src and dst ips. 

![4) using ss to find pid, src, and dst ip](https://github.com/user-attachments/assets/70285b50-d3de-461d-ac59-a1ebc4fe306c)

<br />
<br />
Using "sudo ss dport == 4444 -tnp" to display active TCP connections with a destination port of 4444, showing numerical addresses and port numbers, along with the associated process IDs and program names. Here's a breakdown:
sudo: Runs the command with root privileges,
ss: Socket statistics command,
dport == 4444: Filters for connections with a destination port of 4444,
-t: Shows only TCP connections,
-n: Displays numerical addresses and port numbers,
-p: Shows the PID and name of the program using the connection.

![5) using ss for dport tnp](https://github.com/user-attachments/assets/af56731c-de53-44a0-85f7-9a69f5d0295f)

<br />
<br />
Using "sudo lsof -i -n -P" to list all open network connections and their associated processes with root privileges. Here's what each option does:
-i: Shows network connections (Internet sockets),
-n: Prevents DNS resolution, displaying IP addresses numerically,
-P: Prevents port number to service name conversion, showing port numbers.

![6)lsof to find notmalware](https://github.com/user-attachments/assets/72a3151b-05f1-4e8d-bc1e-a02d68fff39e)

<br />
<br />
Using "sudo lsof -p 3115" to look up process id 3115 of notmalware.elf. 

![7) lsof pid 3115 and sha256](https://github.com/user-attachments/assets/c0eb560c-7f90-4a12-b98c-3d541bd4d08f)

<br />
<br />
