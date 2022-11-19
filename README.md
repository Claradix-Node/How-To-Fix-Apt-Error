# How-To-Fix-Apt-Error

When you use `apt-get update` it verifies if the same update indexes need downloading, if not it does not download the same updated indexes again.
* `Hit` means apt checked the timestamps on package list, those match and there are no changes.
* `Ign` means there are no changes in the pdiff index file, it wont bother downloading it again.
* `Get` means apt checked the timestamps on package list, there were changes and will be downloaded.

# apt-get update fails to fetch files, "Temporary failure resolving..." error.
1. Insidie WSL2, create or append file `/etc/wsl.conf`
2. Put the following lines in the file in order to ensure the your DNS changes do not get blown away
```
sudo tee /etc/wsl.conf << EOF
[network]
generateResolvConf = false
EOF
```
3. **In a `cmd` window**, run `wsl --shutdown`
4. Start WSL2
5. Run the following inside WSL2 (line with `search` is optinal)
```
sudo rm -rf /etc/resolv.conf
sudo tee /etc/resolv.conf << EOF
search yourbase.domain.local
nameserver 8.8.8.8
nameserver 1.1.1.1
EOF
```
