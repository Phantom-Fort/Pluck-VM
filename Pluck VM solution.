# Pluck VM Solution

- **Operating System:** Ubuntu
- **Machine Name:** Pluck

### Analysis:
1. **Performed netdiscover scan to discover the machine’s IP.**

   ![Netdiscover scan](./images/1.png)

2. **Performed a basic Nmap scan to see active ports.**

   ![Nmap Scan](./images/2.png)

3. **HTTP port is open, so I opened the page on my browser.**

   ![Pluck webpage](./images/3.png)

   I found nothing of interest in the source code, so I continued to dig deeper.

4. **Performed a basic directory enumeration using Gobuster with the `big.txt` wordlist.**

   ![Directory enumeration](./images/4.png)

   I found a directory named `/pluck`.

5. **Opened the `/pluck` directory in the browser.**

   ![/pluck directory webpage](./images/5.png)

6. **Found a login page on `/pluck` that requires a password, which we do not have.**

   ![Pluck login page](./images/6.png)

7. **Performed a directory enumeration using `dirb` on Kali Linux.**

   ![Directory enumeration on the /pluck webpage](./images/7.png)

8. **Found some promising directories to investigate.**

   ![/pluck/robots.txt webpage](./images/8.png)

9. **Opened the `robots.txt` file and found an interesting file named `/s3cr3t.txt`. I opened that directory.**

   ![/s3cr3t.txt](./images/9.png)

10. **Used the login info from `/s3cr3t.txt` to sign in on `/login.php`.**

    ![/login.php](./images/10.png)
    ![/login.php](./images/11.png)

    Unfortunately, there was nothing of interest, but I discovered that Pluck 4.7.16 is vulnerable to Local File Injection.

11. **Pluck 4.7.16 Exploit — [Exploit-DB Link](https://www.exploit-db.com/exploits/50826)**

    ![Exploit.db](./images/12.png)

12. **Used the vulnerability to inject a reverse shell into the machine.**

13. **Downloaded `rev_shell.py` and `shell.tar` from [Cyberw1ng’s Bug Bounty GitHub repository](https://github.com/Cyberw1ng/Bug-Bounty).**

    ![Python reverse shell upload](./images/13.png)

14. **Executed a command on the web shell.**

    ![web shell](./images/14.png)

15. **Set up a netcat listener on port 2929.**

    ![netcat](./images/15.png)

16. **Used the reverse shell command on the web shell.**

    ![reverse shell](./images/16.png)
    ![Shell on my terminal](./images/17.png)
    ![shell](./images/18.png)
    ![privilege escalation](./images/19.png)
    ![Root flag](./images/20.png)

**Root Flag:** `eacb474b122937f83b04d9050f0cfc23b89d0c2d3a79c57d928d4472089df2cc`
