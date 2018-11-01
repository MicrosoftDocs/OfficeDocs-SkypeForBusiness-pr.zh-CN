---
title: 删除现有注册器配置设置
TOCTitle: 删除现有注册器配置设置
ms:assetid: ae43cd75-cae4-4f78-b037-779a2cdb583b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182571(v=OCS.15)
ms:contentKeyID: 49313916
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除现有注册器配置设置

 

_**上一次修改主题：** 2013-02-23_

按照以下步骤删除注册器。

## 删除注册器

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到网络中部署了 Lync Server 2013 的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“安全性”，然后单击“注册器”。

4.  在“注册器”页上的搜索字段中，键入要删除的注册器的全部或部分名称。

5.  在列表中，单击所需的注册器，再单击“编辑”，然后单击“删除”。

6.  单击“确定”。

## 使用 Lync Server 命令行管理程序 Cmdlet 删除注册器配置设置

您也可以使用 Lync Server 命令行管理程序和 **Remove-CsProxyConfiguration** cmdlet 删除注册器配置设置。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 删除一组特定的注册器安全设置

  - 以下命令会删除应用到边缘服务器 atl-edge-011.litwareinc.com 的注册器安全设置：
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

## 删除应用到站点范围的所有注册器安全设置

  - 以下命令会删除应用到注册器服务的所有注册器安全设置：
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

## 删除允许 NTLM 身份验证的所有注册器安全设置

  - 以下命令会删除允许使用 NTLM 进行客户端身份验证的所有注册器安全设置：
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

有关详细信息，请参阅 [Remove-CsProxyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsProxyConfiguration)。

