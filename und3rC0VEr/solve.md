# und3rC0VEr

After launching the virtual machine, we need to enter the correct password. According to the task condition, the password is the flag.

![image](https://github.com/user-attachments/assets/f957d238-6d1a-4e9f-91f8-b83bdeb0219d)

Through GRUB, we do not have the ability to reset the password.
![image](https://github.com/user-attachments/assets/a3cefef4-42fa-4cff-8765-d71ff080f904)

Therefore, the option remains to take the router-disk1 disk image and run it on an existing virtual machine with a Debian, Kali, or Ubuntu operating system.
![image](https://github.com/user-attachments/assets/b9a633d8-b1a5-400f-ac60-20033b934053)


After adding the disk, start the virtual machine and press F12. Select the disk with the installed Debian, Kali, or Ubuntu operating system.
![image](https://github.com/user-attachments/assets/c702dbcd-7134-4ca6-a899-9c4abf735d02)

To browse the disks, use the following command:
```fdisk -l```
![image](https://github.com/user-attachments/assets/8f6eec5a-f7fb-43fc-9ead-b848f26cbd48)

And we need to mount the partition /dev/sdb4. Let's create a directory where we will mount.
```mkdir +x /mnt/recovery```

![image](https://github.com/user-attachments/assets/c3af891f-e82d-4992-a0aa-194d38fbfda3) The error says that memory allocation is not possible.

We are restoring the superblock using its backup from '/dev/sdb5'
```e2fsck -b 32768 /dev/sdb5```
![image](https://github.com/user-attachments/assets/29caa62f-a936-46fa-83fa-f4cee3706f7e)

Let's remount it.
```mount /dev/sdb5 /mnt/recovery/```
And let's check the contents of the 'recovery' directory.
```ls -al```
![image](https://github.com/user-attachments/assets/b290ce42-6333-4ace-9b47-239ade896afa)

Let's view the contents of the ovf-env.xml.
```cat ovf-env.xml```
![image](https://github.com/user-attachments/assets/ae77ceea-81c6-4691-b084-1863f7568a73)
And here we see the password for the admin user, which is our flag
##nite{pwn_m3_d4ddy}
