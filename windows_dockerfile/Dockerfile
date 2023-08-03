# 使用 Windows Server Core 镜像作为基础镜像  
FROM mcr.microsoft.com/windows/servercore:1903  
  
# 安装 PowerShell 和远程桌面连接工具  
RUNpowershell Add-AppxPackage -Path C:\windows\system32\Windows.UI.Xaml.dll.mui -Path C:\windows\system32\Windows.winmd  
RUN powershell Add-AppxPackage -Path C:\windows\system32\Microsoft.UI.Xaml.dll -Path C:\windows\system32\Microsoft.UI.Xaml.resources.dll  
RUN powershell Add-AppxPackage -Path C:\windows\system32\Microsoft.Windows.UI.dll -Path C:\windows\system32\Microsoft.Windows.UI.resources.dll  
RUN powershell Add-AppxPackage -Path C:\windows\system32\Microsoft.Windows.DeviceRuntime.dll -Path C:\windows\system32\Microsoft.Windows.DeviceRuntime.resources.dll  
RUN powershell Add-AppxPackage -Path C:\windows\system32\runtimebroker.exe  
  
# 启用远程桌面连接  
RUN Set-NetFirewallRule -Name "RDP-TCP" -DisplayName "Remote Desktop" -Action Allow -Protocol TCP -LocalPort 3389  
  
# 暴露远程桌面端口  
EXPOSE 3389