Download and install git https://git-scm.com/downloads<br>
Download and install VirtualBox https://www.virtualbox.org/wiki/Downloads<br>
Download and install vagrant https://www.vagrantup.com/downloads.html<br>

git clone https://github.com/fossology/fossology.git<br>
cd fossology
git config --local core.autocrlf false<br>
git rm --cached -r .<br>
git reset --hard<br>
Check if port 8081 is already being used. If it is, edit Vagrantfile and replace 8081 with a port that is available.<br>
vagrant up<br>

