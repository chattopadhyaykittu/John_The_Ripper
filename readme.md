**John The Ripper**

![Alt text](https://github.com/chattopadhyaykittu/John_The_Ripper/blob/main/Screenshot%202022-03-13%20at%2010.46.51%20PM.png?raw=true "Title")


[Source](https://www.legallybreaking.com/discussion/192/john-the-ripper-cracking-offline-passwords)

**Introduction**

-   John the Ripper is a tool to crack passwords(to test for
    vulnerability) developed by Openwall.

-   It was initially released for UNIX-based systems but now available
    across multiple platforms (Windows, Linux, MacOS) and it is open
    source.

-   One of the best tools to test the strength of passwords, and crack
    them through dictionary attacks.

-   Claimed to be highly reliable in comparison to its counterparts like
    hashcat.

**John The Ripper (Useful Links):**

-   It can be downloaded from [here](https://www.openwall.com/john/)

-   [John The Ripper
    Tutorial](https://www.hackingarticles.in/beginner-guide-john-the-ripper-part-1/)

-   [John The Ripper on Kali
    Linux](https://www.youtube.com/watch?v=XjVYl1Ts6XI)

-   It comes pre-installed with Kali Linux and and can be run from the
    terminal as shown below:

![Alt text](https://github.com/chattopadhyaykittu/John_The_Ripper/blob/main/Picture%201.png?raw=true "Title")


*Version 1.9.0-jumbo -1 bleeding*

![Alt text](https://github.com/chattopadhyaykittu/John_The_Ripper/blob/main/1.png?raw=true "Title")

[Source](https://info.varonis.com/hubfs/Imported_Blog_Media/Reasons-To-Use-John-The-Ripper.png?hsLang=en)

**What is Password Hashing?**

Hashing is a data scrambling function that accepts readable text and
converts it into an entirely new string of a specific length.

It is practically impossible to reverse, unlike other encryption methods
that transform data. All the passwords are saved in hashes and not as
plaintext. So, if hackers gain their hands on a database full of hashed
passwords, decoding them is pointless. However, hackers have other
options for obtaining the password.

![Alt text](https://github.com/chattopadhyaykittu/John_The_Ripper/blob/main/2.png?raw=true "Title")


[Source](https://www.thesslstore.com/blog/difference-encryption-hashing-salting/)

**Types of users for John The Ripper**

-   **Whitehat Hackers** - To check how vulnerable a password which is
    used by a system is

-   **Blackhat Hackers** - To gain access to systems by cracking the
    passwords for malicious activities.

**Data Breach News :**

-   [Latest data breach news](https://globalnews.ca/tag/data-breach/)

-   [Hacking Password
    Hashes](https://medium.com/@cmcorrales3/password-hashes-how-they-work-how-theyre-hacked-and-how-to-maximize-security-e04b15ed98d)

**Attack Types in John The Ripper**

1)  **Dictionary Attack:** The tool chooses passwords out of a huge list
    of terms, phrases, and probable passwords taken from leaked data or
    breaches. To find the right password, the tool has to input each
    password from that list. It is called Dictionary attack as it makes
    use of predefined words in an English dictionary.

> For example: In an online attack, the hackers will try to log in or
> get entry in the same way that every user would. If the attacker has a
> set of possible passwords, this form of attack works even better. If
> the hack takes a while, a sysadmin or the actual user may notice it.

2)  **Brute-force Attack:** The tool prompts the user to set a few
    parameters, such as the minimum and maximum lengths of the correct
    password, as well as the types of characters it can hold and where
    they should appear. Finding the optimum brute-forcing arrangement
    requires some judgment and knowledge. JtR then attempts to find all
    possible combinations as per the parameters set by the user. When it
    comes across a match, it informs the user. This attack is very
    efficient but it takes too much time to conclude.

> For example: Uppercase alphabets, special characters, and numerals,
> such as ABC32@\$, should all be included in the string you use to
> crack passwords.

> On a perfect match, the user receives a password, although this
> efficient process is very slow. In fact, a machine will take almost
> ten years to guess a 10-character password that contains upper and
> lower case letters, digits, and special characters.

3)  **Rainbow Tables:** If there is a large list of hashed passwords,
    Rainbow Tables can be efficient. Here, a list of password hashes
    generated from commonly used passwords is matched to a pre-existing
    data dump to determine the right plaintext password. Since the
    hashed data is pre-arranged, rainbow tables are faster than
    brute-force attacks.

> For example: A hacker exploits a flaw in an organization\'s Active
> Directory to acquire accessibility to password hashes. They use a
> rainbow table attack to decode the hashes into plaintext passwords
> once they get the sequence of hashes.

**Useful Link**

-   [John The Ripper Attack
    Types](https://www.csoonline.com/article/3564153/john-the-ripper-explained-an-essential-password-cracker-for-your-hacker-toolkit.html)

-   [Hash Formats of John The
    Ripper](https://pentestmonkey.net/cheat-sheet/john-the-ripper-hash-formats)

**Modes in John the Ripper**

![Alt text](https://github.com/chattopadhyaykittu/John_The_Ripper/blob/main/90.png?raw=true "Title")

[Source](https://www.varonis.com/blog/john-the-ripper)

1)  **Single crack mode:** This mode is considered to be the fastest. As
    a result, it is the one cracking should start with. This mode is
    useful when a user creates a password for an account using
    information from the username (e.g. username: username1234).

- **Syntax:** john [mode option][password file\]
> john --single --format=raw-sha1 crack.txt 
> where the mode is single, hash format is RAW-SHA1 and the hash is
> stored in crack.txt

2)  **Wordlist Mode:** This is the most basic cracking mode that John
    endorses. You only need to provide a wordlist (a text file with one
    word per line) and some password files. Word mutilation rules can
    also be enabled. Once all of the rules are activated, they will be
    implemented to each and every line in the wordlist file, resulting
    in numerous potential passwords for every source word.

- **Syntax:** john [wordlist][options] [password file]

> john --wordlist=/usr/share/john/password.lst --format=raw-sha1 crack.txt

**OR**

> john --wordlist=/usr/share/wordlists/rockyou.txt --format=raw-sha1 crack.txt

> where the wordlist is the mode, password.lst is the text file inside
  john the ripper containing a directory of passwords, the format is
  RAW-SHA1 and the hashed file is stored in crack.txt

 rockyou.txt is Kali Linux's own password list, a huge password dictionary

3)  **Incremental Mode:** This is the most powerful password cracking
    option; it can examine all potential character combinations. Though,
    it is anticipated that cracking here would never end due to the vast
    number of permutations and users will have to terminate it sooner.
    It is one of the reasons why, in order to break as many passwords as
    feasible in a short amount of time, this method handles trigraph
    frequencies separately for each letter position and password length.

> **Syntax:** john [Incremental:MODE] [password file]

> john --incremental crack.txt
  where the mode is incremental and crack.txt is the file in which the hash is stored

**Useful Link**

-   [John The Ripper cracking
    modes](https://www.openwall.com/john/doc/MODES.shtml)

-   [rockyou.txt
    file](https://github.com/brannondorsey/naive-hashcat/releases/download/data/rockyou.txt)

**Cracking Compressed Files**

-   **Cracking RAR Password Hash**

   Create a compressed encrypted rar file

   Creating a hash of the password

  **Syntax**: rar2john \[location of key\]

  Finally cracking it using Ripper

![Alt text](https://github.com/chattopadhyaykittu/John_The_Ripper/blob/main/3.png?raw=true "Title")


>   a = Add files to archive

> hp\[password\] = Encrypt both file data and headers

>  This command will encrypt text.txt into text.rar

> rar2john text.rar command is used to convert the password into hash
  which john can crack

![Alt text](https://github.com/chattopadhyaykittu/John_The_Ripper/blob/main/4.png?raw=true "Title")

Finally the password is cracked

-   **Cracking ZIP Password Hash**

 Encrypt a zip file

 Convert the password to hash


>**Syntax:** zip2john [location of key]


 Finally crack it using Ripper
   
 - ![Alt text](https://github.com/chattopadhyaykittu/John_The_Ripper/blob/main/5.png?raw=true "Title")


> e = Encrypt

> r = Recursive into directories

-   **Cracking SSH Password Hash**


 To test the cracking of the private key, have to create a set of new
 private keys using the command **ssh-keygen**

 After running the command, it asks for the location (we can use any
  location or leave it as default)

 Then it asks for the passphrase and after we enter the password once
  again, we successfully generate the key.

 In order for john to crack, it's format is changed using the syntax
  **ssh2john \[location of key\]**

 After it is converted into a crackable hash, JtR is used on this
  hash.

![Alt text](https://github.com/chattopadhyaykittu/John_The_Ripper/blob/main/6.png?raw=true "Title")

![Alt text](https://github.com/chattopadhyaykittu/John_The_Ripper/blob/main/7.png?raw=true "Title")


> Finally the hash is cracked

**Cracking User Credentials**

 The user's password is stored in a shadow file at the location
 **/etc/shadow**, which is a system file where the encrypted user
 password is stored

 Cracking the credentials of all users

> **unshadow /etc/passwd /etc/shadow \> crack.txt**


> (unshadow command is combining the /etc/passwd and /etc/shadow files
  for helping john to gather information required to crack the
  credentials of all users and the hash is stored inside crack.txt)

> john \--wordlist=/usr/share/wordlists/rockyou.txt crack.txt

> After using this command, the credentials will be cracked

**Useful Link:**

-   [Hacking
    Article](https://www.hackingarticles.in/beginners-guide-for-john-the-ripper-part-2/)

-   [Guide to John The Ripper](https://miloserdov.org/?p=5191)

**Competitors**

- Hashcat is one of John the Ripper\'s main rivals. It, similar to John
 the Ripper, is a command-line programme that can crack a wide range of
 password types. Hashcat, on the other hand, has greater support for
 cracking passwords utilizing your graphics card. Hashcat is way quicker
 than John the Ripper if you have a strong GPU.

 > There is also a Hash [Suite](https://hashsuite.openwall.net/) which has
   a modern GUI and can crack 13 different hash types.

**Conclusion**

- JtR has risen up to be one of the best password cracking tools. It is
  not very beginner-friendly considering it involves numerous steps to run
  it. But it targets sysadmins and regular users and has everything needed
  to crack several hash types.

**References:**

-   <https://www.csoonline.com/article/3564153/john-the-ripper-explained-an-essential-password-cracker-for-your-hacker-toolkit.html#:~:text=First%20released%20in%201996%2C%20John,crack%20passwords%20via%20dictionary%20attacks>

-   <https://nordpass.com/blog/password-hash/>

-   <https://nordpass.com/blog/what-is-a-dictionary-attack/>

-   <https://techofide.com/blogs/how-to-use-john-the-ripper-john-the-ripper-password-cracker-techofide/>

-   <https://www.beyondidentity.com/glossary/rainbow-table-attack>

-   [https://www.openwall.com/john/doc/MODES.html](https://www.openwall.com/john/doc/MODES.shtml)
