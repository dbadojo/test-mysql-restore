Restore the whole mysql instance from this tarball. It is a MySQL 5.6 cold backup.

Once you have successfully done that you need to get the passphrase for the next restore test.

To get the passphrase to de-crypt restore-3.tgz.cpt use this SQL to get the password:

select password from sakila.staff where staff_id = 3;

You will need to use aes-decrypt to decrypt the password:
The key_str was SHA2('restore-2',512).
The password was converted from binary to hex using HEX().

Hint: use UNHEX() on the password first then pass to AES_DECRYPT(crypt_str,key_str)

https://dev.mysql.com/doc/refman/5.6/en/encryption-functions.html#function_aes-encrypt
