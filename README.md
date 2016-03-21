Download and install git https://git-scm.com/downloads<br>
Download and install VirtualBox https://www.virtualbox.org/wiki/Downloads<br>
Download and install vagrant https://www.vagrantup.com/downloads.html<br>

git clone https://github.com/fossology/fossology.git<br>
cd fossology<br>
git config --local core.autocrlf false<br>
git rm --cached -r .<br>
git reset --hard<br>
Check if port 8081 is already being used. If it is, edit Vagrantfile and replace 8081 with a port that is available.<br>
Run cmd as Administrator (Find cmd in the Start Menu, it's usually under Accessories, right click, select Run as Administrator)<br>
cd fossology<br>
vagrant up<br>
Access http://localhost:8081/repo/<br>
Login as fossy/fossy<br>
Create an archive with all your source code using one of the file formats listed by Fossology. It may be necessary to use multiple files if a single file would exceed the maximum size listed by Fossology.<br>
Select Upload->From File and upload your archive.<br>
