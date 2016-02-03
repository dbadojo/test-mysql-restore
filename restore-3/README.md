Restore the whole mysql instance from this tarball. 
It is a full backup taken using Percona xtrabackup using the following commands
xtrabackup --backup --target-dir=/root/restore-3/backup
xtrabackup --prepare --target-dir=/root/restore-3/backup

Once you have successfully done the restore, you need to get the passphrase for the next restore test.

To get the passphrase to de-crypt restore-4.tgz.cpt use this SQL to get the password:

select password from sakila.staff where staff_id = 3;

You will need to use aes-decrypt to decrypt the password:
The key_str was SHA2('restore-3',512).
The password was converted from binary to hex using HEX().

Hint: use UNHEX() on the password first then pass to AES_DECRYPT(crypt_str,key_str)

https://dev.mysql.com/doc/refman/5.6/en/encryption-functions.html#function_aes-encrypt
