# Device-does-not-provide-enough-allocatable-device-memory-to-handle-this-attack

I'm getting this error when trying to load an MD5 hash into memory and around 10k words from a list. Output_1 was ran on the physical machine (windows11) while Output_2 was from Kali running on virtualbox.

Command Prompt on the host machine said there was not enough allocatable device memory and hashcat task was not completed while Kali, the virtual machine actually completed the task notwithstanding.

Question is: Why is it like this

Here's the complete output and version:

                                                   
                                                   
                                                   OUTPUT_1
                                                   

I'm getting this error when trying to load an MD5 hash into memory and around 10k words from my library
My OCL device is a 750Ti with 2G VRAM.

As it works with smaller files, I can, of course, split the file and script hashcat to iterate through them, but would't be better if HC could handle this scenarios by itself? I don't thinl it's that uncommon.

Here's the complete output and version:


OUTPUT_1
C:\Users\USER\Downloads\hashcat-6.2.5\hashcat-6.2.5>hashcat.exe -a 0 -m 0 hashes.txt C:\Users\USER\Downloads\hashcat-6.2.5\hashcat-6.2.5\10k-most-common.txt
hashcat (v6.2.5) starting

OpenCL API (OpenCL 1.2 ) - Platform #1 [Intel(R) Corporation]
=============================================================
* Device #1: Intel(R) HD Graphics 4400, 768/1629 MB (203 MB allocatable), 20MCU
* Device #2: Intel(R) Core(TM) i5-4300U CPU @ 1.90GHz, skipped

Minimum password length supported by kernel: 0
Maximum password length supported by kernel: 256

Hashes: 1 digests; 1 unique digests, 1 unique salts
Bitmaps: 16 bits, 65536 entries, 0x0000ffff mask, 262144 bytes, 5/13 rotates
Rules: 1

Optimizers applied:
* Zero-Byte
* Early-Skip
* Not-Salted
* Not-Iterated
* Single-Hash
* Single-Salt
* Raw-Hash

ATTENTION! Pure (unoptimized) backend kernels selected.
Pure kernels can crack longer passwords, but drastically reduce performance.
If you want to switch to optimized kernels, append -O to your commandline.
See the above message to find out about the exact limits.

Watchdog: Hardware monitoring interface not found on your system.
Watchdog: Temperature abort trigger disabled.

* Device #1: Not enough allocatable device memory for this attack.

Started: Tue May 24 09:27:27 2022
Stopped: Tue May 24 09:27:50 2022





					                                                            	OUTPUT_2
 ┌──(emissary㉿kali)-[~]
└─$ hashcat -a 0 -m 0 /home/emissary/Downloads/hashes/hashes.txt /home/emissary/Downloads/hashes/10k-most-common.txt
hashcat (v6.1.1) starting...

OpenCL API (OpenCL 1.2 pocl 1.6, None+Asserts, LLVM 9.0.1, RELOC, SLEEF, DISTRO, POCL_DEBUG) - Platform #1 [The pocl project]
=============================================================================================================================
* Device #1: pthread-Intel(R) Core(TM) i5-4300U CPU @ 1.90GHz, 1423/1487 MB (512 MB allocatable), 1MCU

Minimum password length supported by kernel: 0
Maximum password length supported by kernel: 256

Hashes: 1 digests; 1 unique digests, 1 unique salts
Bitmaps: 16 bits, 65536 entries, 0x0000ffff mask, 262144 bytes, 5/13 rotates
Rules: 1

Applicable optimizers applied:
* Zero-Byte
* Early-Skip
* Not-Salted
* Not-Iterated
* Single-Hash
* Single-Salt
* Raw-Hash

ATTENTION! Pure (unoptimized) backend kernels selected.
Using pure kernels enables cracking longer passwords but for the price of drastically reduced performance.
If you want to switch to optimized backend kernels, append -O to your commandline.
See the above message to find out about the exact limits.

Watchdog: Hardware monitoring interface not found on your system.
Watchdog: Temperature abort trigger disabled.

Host memory required for this attack: 64 MB

Dictionary cache built:
* Filename..: /home/emissary/Downloads/hashes/10k-most-common.txt
* Passwords.: 10000
* Bytes.....: 83017
* Keyspace..: 10000
* Runtime...: 0 secs

Approaching final keyspace - workload adjusted.  

Session..........: hashcat                       
Status...........: Exhausted
Hash.Name........: MD5
Hash.Target......: 8743b52063cd84097a65d1633f5c74f5
Time.Started.....: Tue May 24 09:37:18 2022 (0 secs)
Time.Estimated...: Tue May 24 09:37:18 2022 (0 secs)
Guess.Base.......: File (/home/emissary/Downloads/hashes/10k-most-common.txt)
Guess.Queue......: 1/1 (100.00%)
Speed.#1.........:    22616 H/s (0.58ms) @ Accel:1024 Loops:1 Thr:1 Vec:8
Recovered........: 0/1 (0.00%) Digests
Progress.........: 10000/10000 (100.00%)
Rejected.........: 0/10000 (0.00%)
Restore.Point....: 10000/10000 (100.00%)
Restore.Sub.#1...: Salt:0 Amplifier:0-1 Iteration:0-1
Candidates.#1....: dga9la -> eyphed

Started: Tue May 24 09:33:55 2022
Stopped: Tue May 24 09:37:20 2022




     
                                                                    HOST DEVICE VERSION
Device name	DESKTOP-VV9ELLL
Processor	Intel(R) Core(TM) i5-4300U CPU @ 1.90GHz   2.50 GHz
Installed RAM	8.00 GB (7.90 GB usable)
Device ID	8EF9F489-E642-4FAE-9F1D-6865936F78D7
Product ID	00330-80214-20243-AA229
System type	64-bit operating system, x64-based processor
Pen and touch	Pen and touch support with 10 touch points
