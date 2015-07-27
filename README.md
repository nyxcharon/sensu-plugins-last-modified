sensu-plugins-last-modified
===================================

Functionality
-------------------------
Retrieves the headers for a file via HTTP and checks the last modified time. If this time
is within the threshold you specify, it passes, otherwise it fails.  

Files
-------------------------
* bin/check-last-modified.rb

Usage
-------------------------
Flags:
* -u/--url - The URL to the file to be checked [required]
* -t/--time - The time in seconds the file should be updated by. [required]
* -U/--username - The user to authenticate as
* -a/--password - The password to authenticate with

Check a publicly accessible file and make sure it's updated  within every 24 hours:
```
check-last-modified.rb -u http://somesite.com/somefile.zip -t 86400
```

Check a file with http authentication every 5 minutes.
```
check-last-modified.rb -u http://somesite.com/somefile.zip -t 300 -U myuser -a mypassword
```

License
----------------------------
Released under the same terms as Sensu (the MIT license); see LICENSE for details.
