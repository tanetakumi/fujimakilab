# fujimakilab
Setting up the server in Fujimaki Lab.

## SSH
From the local environment, you can enter with password authentication, while from outside, you can only enter with the public key authentication.

### How to set up the public key

1. Run the ssh-keygen command to generate your private key and public key __on your PC__.
    ```
    C:\Users\username>ssh-keygen
    Generating public/private rsa key pair.
    Enter file ... :        (Press Enter)
    Enter passphrase ... :  (Press Enter)
    Enter same ... :        (Press Enter)
    ```

2. Create a '.ssh' folder directly under your home directory __on the server__.
    ```
    ssh -p <port> <username>@<ip> ... connect to the server
    mkdir .ssh
    ```

3. Send the authorized_keys (__on your PC__)
    ```
    scp -P <port> C:\Users\nutan\.ssh\id_rsa.pub <username>@<address>:~/.ssh/authorized_keys
    ```

4. Change the permissions of authorized_keys __on the server__.
    ```
    chmod 600 .ssh/authorized_keys
    ```

## Connecting with VScode

1.  Edit your "~/.ssh/config" file
    
    Add this host to config file
    ```
    Host fujimakilab
        HostName <address>
        User <username>
        Port <port>
        UserKnownHostsFile /dev/null
        PasswordAuthentication no
        IdentityFile C:\Users\<username>\.ssh\id_rsa
        IdentitiesOnly yes
        ForwardAgent yes
        ForwardX11 yes
        ForwardX11Trusted yes
        ForwardX11Timeout 596h
        ServerAliveInterval 300
        ServerAliveCountMax 5
    ```
2.  install VScode extention "Remote - SSH"

3.  Press the green button in the bottom left corner of VScode

4.  Select the "Connect to Host" and "Host fujimakilab"



## Docker Container

### __Simulation__
I will write this session.


## Environment

- python3.10
- python3.9
- JoSIM
- Jsim, Jsim_n, pJsim, pJsim_n
- docker
- node.js



