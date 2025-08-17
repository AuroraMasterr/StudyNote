## 常用指令

### du（disk usage）

```shell
du -h --max-depth=1	[path]		# 统计[path]一级子目录的磁盘占用
```

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

```shell
rsync -avz --progress [source] [destination]	# 以压缩状态传输，并且显示传输进度
```

- 用于本地计算机与远程计算机之间同步文件。不支持两台远程计算机之间的同步，需要在本地中转。
- 可以当作文件复制命令代替 `cp`
- `rsync` 会检查发送方和接收方已有的文件，仅传输有变动的部分（默认规则是文件大小或修改时间有变动）

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

```
tmux ls 	# 查看当前所有会话
tmux new -s <session-name>			# 创建新会话<session-name>
tmux attach -t <session-name>		# 连接到会话<session-name>
```

![image-20250630120115840](assets/image-20250630120115840.png)  

### ps（process status）

![image-20250701151612892](assets/image-20250701151612892.png)

<img src="assets/image-20250701150319157.png" alt="image-20250701150319157" style="zoom:50%;" /> 

<img src="assets/image-20250701152138669.png" alt="image-20250701152138669" style="zoom:50%;" /> 

<img src="assets/image-20250701152208462.png" alt="image-20250701152208462" style="zoom:67%;" /> 

### mv（move file）

![image-20250701152820568](assets/image-20250701152820568.png) 

### cp（copy file）

![image-20250701152858056](assets/image-20250701152858056.png)

### rm（remove）

```shell
rm -rf [dir-name]	# 强制删除目录[dir-name]	(删除目录必须加-r)
```

<img src="assets/image-20250802150958221.png" alt="image-20250802150958221" style="zoom: 80%;" /> 

## 文档编辑

### vim

![image-20250701152409557](assets/image-20250701152409557.png) 

### sort

```shell
sort [file-name]				# 把文件的所有行按照第一列的ASCII码排序
sort -h [file-name]			# 如果第一列是人类可读的数值，则按照第一列的人类可读数值排序
sort -k [sort-index] [file-name]		# 按照第 sort-index 列排序
sort -k 2 [file-name]		# 按照第 2 列排序
```

- Linux sort 命令用于将文本文件内容加以排序。

  sort 可针对文本文件的内容，以行为单位来排序。

<img src="assets/image-20250811141902218.png" alt="image-20250811141902218" style="zoom:50%;" /> 

## Git

### commit

```shell
git commit -m [message]			# 提交暂存区到本地仓库中
git commit -am [message]		# 把修改提交到暂存区，然后把暂存区提交到本地仓库。新增文件不会被提交到暂存区。
git commit --amend				# 修正最近一次 commit
```

### checkout

```shell
git checkout <branch-name>		# 切换到分支<branch-name>
git checkout -b <new-branch-name>	 # 从当前分支创建一个新分支并切换
git checkout <commit-hash>		# 切换到特定的提交状态，进入"分离头指针"状态，只能查看历史记录，而不能进行分支操作。
```

### push

```shell
git push <远程主机名> <本地分支名>:<远程分支名>	# 把本地的分支<本地分支名>推送到主机<远程主机名>的分支<远程分支名>上
git push -u <远程主机名> <本地分支名>		       # 推送的时候设置上游分支，新分支首次推送到远程时使用
git push origin --delete <branch-name>		  # 删除远程分支 <branch-name>
```

- 克隆一个项目的时候，git 会自动帮我们把远程主机起名为 `origin`
- 本地分支名和远程分支名一致时，简写为 `git push <远程主机名> <本地分支名> `

### branch

```shell
git branch				# 查看所有本地分支
git branch -r			# 查看所有远程分支
git branch -a			# 查看所有本地和远程分支
git branch -d <branch-name>		# 删除本地分支<branch-name>, 该分支被合并后才能删除
git branch -D <branch-name>		# 强制删除本地分支<branch-name>, 忽略任何未合并的更改
```

### reset

```shell
git reset --soft HEAD~1			# 撤销最近一次commit，保留修改
```

### stash

```shell
git stash				# 临时保存当前工作目录的更改
git stash list  		# 查看存储的进度
git stash apply			# 应用最近一次存储的进度
git stash pop			# 应用并删除最近一次存储的进度
git stash clear			# 清空所有存储
git stash show -p <stash-name>		# 查看某个 stash 的详细内容
git stash show -p stash@{0}		# 查看最近一次 stash 的详细内容
```

### merge

```shell
git merge <branch-name>			# 把<branch-name>分支的更改合并到当前分支
git --no-ff merge <branch-name>		# 禁用快进合并，强制创建一个合并的 commit，保留合并历史
```

## NVIDIA 驱动安装

Driver 下载地址：https://www.nvidia.com/en-us/drivers/

fabricmanager下载地址：https://developer.download.nvidia.cn/compute/cuda/repos/ubuntu2004/x86_64/

查看 fabricmanager 版本

```shell
apt list --installed | grep nvidia-fabricmanager
```

卸载旧版本，安装新版本

```shell
dpkg -r nvidia-fabricmanager-570 		# 卸载旧版本NVIDIA-Fabric Manager
dpkg -r nvidia-fabricmanager-dev-570    # 卸载旧版本Nvidia-Fabric-Manager-devel
wget https://developer.download.nvidia.cn/compute/cuda/repos/ubuntu2004/x86_64/nvidia-fabricmanager-550_550.163.01-1_amd64.deb
dpkg -i nvidia-fabricmanager-550_550.163.01-1_amd64.deb			# 安装目标版本
```

启动 fabricmanager

```shell
sudo systemctl enable nvidia-fabricmanager   # 配置Fabric Manager服务随实例开机自启动
sudo systemctl start nvidia-fabricmanager    # 启动Fabric Manager服务
sudo systemctl status nvidia-fabricmanager    # 查看Fabric Manager服务是否正常启动，回显active（running）表示启动成功
sudo systemctl unmask nvidia-fabricmanager    # 用于解决Fabric Manager is masked报错
```

