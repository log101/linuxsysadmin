
## How to grant sudo access to your user?

Working with root privilages might result in fatal mistakes. So you have to make
 sure that you're not working with sudo. But that doesn't mean you can't have su
per user privilages. With sudo mechanism you can be super-user per-command basis
. Follow the instructions!

1. Check if you are already included in the sudoers list.
`$ sudo uptime`
2. If you're asked for password you're seeing how long your system has been running, then you're already done! If not:
3. If you're not root, run `su` and enter the "root" password, not user password.
4. Navigate to `/etc/sudoers.d`
5. Create a new file with a name you want, your username is a good choice.
`$ touch your-user-name`
6. Add this line to the file with your favorite text editor.
`your-user-name ALL=(ALL) ALL`
7. Save and exit.
8. Now you need to change the permissions for the file. (We don't want strangers to edit your permissions!)
`chmod 440 your-user-name`
9. After these steps, exit from the root shell and using sudo again. It should work now!

