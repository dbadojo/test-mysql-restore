# test-mysql-restore
MySQL restoration tests.

These tests are designed to test your ability to do basic restores and recoveries of a MySQL database.

Each restore gets progressively more complex.

The key feature is, once you are successfully restored the MySQL database you will get the encryption key/passphrase
to do the next test.

Use: ccrypt -d <filename>.cpt to decrypt the file.


Requirements:
Virtualbox and vagrant if using a virtual machine for running the MySQL instance.
MySQL 5.6
ccrypt or equivalent

A vagrantfile is provided as an example to spawn a simple virtualbox VM with 1Gig of memory to
run the small MySQL database required for the tests.

Once you have completed all the current tests, email dbadojo@gmail.com and we will keep you informed when the next set is ready. If you have ideas for more tests, send them over as well.

