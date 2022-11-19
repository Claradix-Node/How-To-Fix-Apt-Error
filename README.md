# How-To-Fix-Apt-Error

When you use `apt-get update` it verifies if the same update indexes need downloading, if not it does not download the same updated indexes again.
* `Hit` means apt checked the timestamps on package list, those match and there are no changes.
* `Ign` means there are no changes in the pdiff index file, it wont bother downloading it again.
* `Get` means apt checked the timestamps on package list, there were changes and will be downloaded.

# apt-get update fails to fetch files, "Temporary failure resolving..." error.
```
echo "namespace 8.8.8.8" | sudo tee /etc/resolv.conf > /dev/null
```
