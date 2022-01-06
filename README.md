# fujimakilab
Setting up the server in Fujimaki Lab.

## SSH
From the local environment, you can enter with password authentication, while from outside, you can only enter with the public key authentication.

### How to set up the public key

1. Run the ssh-keygen command to generate your private key and public key.
    ```
    C:\Users\username>ssh-keygen
    Generating public/private rsa key pair.
    Enter file ... :        (Press Enter)
    Enter passphrase ... :  (Press Enter)
    Enter same ... :        (Press Enter)
    ```

2. Create a '.ssh' folder directly under your home directory on the server.

3. Send the authorized_keys
    ```
    scp -P <port> ~/.ssh/id_rsa.pub <username>@<address>:~/.ssh/authorized_keys
    ```

4. Change the permissions of authorized_keys.
    ```
    chmod 600 authorized_keys
    ```



