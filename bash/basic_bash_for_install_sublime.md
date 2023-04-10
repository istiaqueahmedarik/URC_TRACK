we want to write a script that will install sublime text then create a file name hello.txt and open it

```bash
#!/bin/bash
# install sublime text
sudo add-apt-repository ppa:webupd8team/sublime-text-3
sudo apt-get update
sudo apt-get install sublime-text-installer
# create a file named hello.txt
touch hello.txt
# open the file
echo "HI" > hello.txt
subl hello.txt

```
