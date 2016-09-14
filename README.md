Download and install git https://git-scm.com/downloads<br>
Download and install VirtualBox https://www.virtualbox.org/wiki/Downloads<br>
Download and install vagrant https://www.vagrantup.com/downloads.html<br>

Launch the git shell and run
```
git clone https://github.com/fossology/fossology.git
cd fossology
git config --local core.autocrlf false
git rm --cached -r .
git reset --hard
```

Check if port 8081 or 5432 are already being used. 
```
netstat -ano
  TCP    0.0.0.0:8081           0.0.0.0:0              LISTENING    33411
  TCP    0.0.0.0:5432           0.0.0.0:0              LISTENING    33411
```

If the ports are being used, edit Vagrantfile in the fossology directory that was created above.

You can also use the process IDs listed at the end of the netstat output to see if the listening process can be shutdown.

Search for the following lines
```
config.vm.network "forwarded_port", guest: 80, host: 8081
config.vm.network "forwarded_port", guest: 5432, host: 5432
```
and replace 8081 or 5432 with a ports that are available.<br>
Run cmd as Administrator (Find cmd in the Start Menu, it's usually under Accessories, right click, select Run as Administrator)<br>
```
cd fossology
vagrant up
```
Access [http://localhost:8081/repo/](http://localhost:8081/repo/) Make sure the port number matches the value configured above<br>
Login as fossy/fossy<br>
Create an archive with all your source code using one of the file formats listed by Fossology. It may be necessary to use multiple files if a single file would exceed the maximum size listed by Fossology.<br>
Select Upload->From File and upload your archive.<p>
Additional information on using FOSSology can be found in the [http://archive15.fossology.org/projects/fossology/wiki/Quickstart](FOSSology Quickstart Guide)

## Troubleshooting
**Problem:** vagrant up fails due to the virtual machine not starting with an error related to VT-x.<br>
**Solution:** VT-x is a bios setting that allows for virtualization. This error is usually due to VT-x not being enabled in the BIOS. The steps to enable VT-x vary from device to device so Google'ing for the steps is usually the best approach.
