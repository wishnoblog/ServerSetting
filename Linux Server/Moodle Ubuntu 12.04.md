#Moodle Ubuntu12.04 系統整備指南

這份文件會解釋如何安裝MOODLE於Linux系統，以及系統上線前需要的調整。

###硬體環境需求

建議環境
  
* **ubuntu 12.04**
* **至少2G記憶體，如果世上線使用的系統建議採用4G以上的記憶體。**
* **至少2G的CPU**
* **最少25GB的硬碟空間，建議使用50G以上的空間。**

###系統整備
* 設定系統IP

`sudo vi /etc/network/interfaces`   

     auto eth0
     iface eth0 inet static  # 固定 (靜態) IP。
     address 140.127.ooo.xxx # IP 位址。
     netmask 255.255.255.0   # 網路遮罩。
     gateway 140.127.qqq.ppp # 預設閘道。
	 dns-nameservers 8.8.8.8 8.8.4.4     #DNS位址 

重新啟動網路

` /etc/init.d/networking restart `



* 設定Proxy

`export http_proxy=`   
寫入   
`~/.bashrc`

* 更新系統

		sudo apt-get update -y   
		sudo apt-get upgrade -y   
		reboot
    
* 安裝VIM

		sudo apt-get install Vim 
    
* 安裝遠端控制

		sudo apt-get install ssh -y
 
* 安裝LAMP

		sudo apt-get install apache2 php5 php5-mysql mysql-server

* 安裝CURL

		sudo apt-get install php5-curl

系統會詢問MYSQL管理者密碼


* 安裝Git
安裝GIT才能取得程式檔案

`sudo apt-get install git-core` 

##開始安裝Moodle

