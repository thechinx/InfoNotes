# System update/upgrade



* **Check for updates**

```
sudo apt update
```

* **Check available updates**

```
sudo apt list --upgradable
```

* **Upgrade system**

```
sudo apt upgrade        
```

* **To remove packages that failed to install completely**

```
sudo apt-get autoclean
```

* **To remove the unwanted software dependencies**

```
sudo apt-get autoremove
```

* **Combining commands**

```
sudo apt update && sudo apt upgrade && sudo apt autoclean && sudo apt autoremove
```
