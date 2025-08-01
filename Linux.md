## 常用指令

### du（disk usage）

<img src="assets/image-20250629014922305.png" alt="image-20250629014922305" style="zoom:67%;" /> 

<img src="assets/image-20250629014949953.png" alt="image-20250629014949953" style="zoom:67%;" /> 

<img src="assets/image-20250629015035185.png" alt="image-20250629015035185" style="zoom:67%;" /> 

<img src="assets/image-20250629015133041.png" alt="image-20250629015133041" style="zoom:67%;" />  

### df（disk free）

<img src="assets/image-20250629015454394.png" alt="image-20250629015454394" style="zoom:67%;" /> 

<img src="assets/image-20250629015509891.png" alt="image-20250629015509891" style="zoom:67%;" /> 

### scp（secure copy）

<img src="assets/image-20250629015740333.png" alt="image-20250629015740333" style="zoom:80%;" /> 

<img src="assets/image-20250629015727889.png" alt="image-20250629015727889" style="zoom:80%;" /> 

<img src="assets/image-20250629015809717.png" alt="image-20250629015809717" style="zoom:80%;" /> 

<img src="assets/image-20250629015843846.png" alt="image-20250629015843846" style="zoom:80%;" /> 

<img src="assets/image-20250629020013881.png" alt="image-20250629020013881" style="zoom:67%;" /> 

### rsync（remote sync）

<img src="assets/image-20250629020149298.png" alt="image-20250629020149298" style="zoom:80%;" /> 

<img src="assets/image-20250629020625112.png" alt="image-20250629020625112" style="zoom:80%;" />  

<img src="assets/image-20250629020343498.png" alt="image-20250629020343498" style="zoom:67%;" /> 

<img src="assets/image-20250629020839182.png" alt="image-20250629020839182" style="zoom:80%;" />  

<img src="assets/image-20250630104917858.png" alt="image-20250630104917858" style="zoom:67%;" /> 

<img src="assets/image-20250629020548673.png" alt="image-20250629020548673" style="zoom: 67%;" />  

### ssh-keygen

<img src="assets/image-20250629021212630.png" alt="image-20250629021212630" style="zoom:67%;" /> 

<img src="assets/image-20250629022147296.png" alt="image-20250629022147296" style="zoom: 80%;" /> 

<img src="assets/image-20250629022226359.png" alt="image-20250629022226359" style="zoom:80%;" />  

<img src="assets/image-20250629022100476.png" alt="image-20250629022100476" style="zoom:80%;" /> 

<img src="assets/image-20250629022300777.png" alt="image-20250629022300777" style="zoom:80%;" /> 

 

### cat（concatenate）

<img src="assets/image-20250629021549530.png" alt="image-20250629021549530" style="zoom:67%;" /> 

<img src="assets/image-20250629021623459.png" alt="image-20250629021623459" style="zoom:67%;" /> 

<img src="assets/image-20250629021707211.png" alt="image-20250629021707211" style="zoom:67%;" /> 

### tmux（terminal multiplexer）

![image-20250630120115840](assets/image-20250630120115840.png)  

### ps（process status）

![image-20250701151612892](assets/image-20250701151612892.png)

<img src="assets/image-20250701150319157.png" alt="image-20250701150319157" style="zoom:50%;" /> 

<img src="assets/image-20250701152138669.png" alt="image-20250701152138669" style="zoom:50%;" /> 

<img src="assets/image-20250701152208462.png" alt="image-20250701152208462" style="zoom:67%;" /> 

### vim

![image-20250701152409557](assets/image-20250701152409557.png) 

### mv

![image-20250701152820568](assets/image-20250701152820568.png) 

### cp

![image-20250701152858056](assets/image-20250701152858056.png)

## git

### commit

```
git commit -m [message]			# 提交暂存区到本地仓库中
```



## NVIDIA 驱动安装

Driver 下载地址：https://www.nvidia.com/en-us/drivers/

fabricmanager下载地址：https://developer.download.nvidia.cn/compute/cuda/repos/ubuntu2004/x86_64/

查看 fabricmanager 版本

```
apt list --installed | grep nvidia-fabricmanager
```

卸载旧版本，安装新版本

```
dpkg -r nvidia-fabricmanager-570   # 卸载旧版本NVIDIA-Fabric Manager
dpkg -r nvidia-fabricmanager-dev-570    # 卸载旧版本Nvidia-Fabric-Manager-devel
wget https://developer.download.nvidia.cn/compute/cuda/repos/ubuntu2004/x86_64/nvidia-fabricmanager-550_550.163.01-1_amd64.deb
dpkg -i nvidia-fabricmanager-550_550.163.01-1_amd64.deb			# 安装目标版本
```

启动 fabricmanager

```
sudo systemctl enable nvidia-fabricmanager   # 配置Fabric Manager服务随实例开机自启动
sudo systemctl start nvidia-fabricmanager    # 启动Fabric Manager服务
sudo systemctl status nvidia-fabricmanager    # 查看Fabric Manager服务是否正常启动，回显active（running）表示启动成功
sudo systemctl unmask nvidia-fabricmanager    # 用于解决Fabric Manager is masked报错
```

