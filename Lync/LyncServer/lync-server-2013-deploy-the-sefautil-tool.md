---
title: 部署 SEFAUtil 池
TOCTitle: 部署 SEFAUtil 池
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945659(v=OCS.15)
ms:contentKeyID: 52061158
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 部署 SEFAUtil 池

 

_**上一次修改主题：** 2016-12-08_

若要部署和管理组内呼叫应答，您需要使用 SEFAUtil 资源工具包工具。该工具是 Lync Server 2013 资源工具包工具的一部分。在安装 SEFAUtil 之前，您的拓扑中必须有一个受信任的应用程序池，将 SEFAUtil 指定为受信任应用程序，然后启用该拓扑。

> [!IMPORTANT]
> Microsoft 统一通信托管 API (UCMA) 3.0 核心 SDK 必须安装在您计划运行 SEFAUtil 工具的任何计算机上。


您可以在您的部署中的任何前端池中运行 SEFAUtil。

> [!NOTE]  
> 有关运行 SEFAUtil 的更多详细信息，请参阅 Technet 博客文章“如何运行 SEFAutil？”，网址为 <a href="http://go.microsoft.com/fwlink/?linkid=278940" class="uri">http://go.microsoft.com/fwlink/?linkid=278940</a>。



## 部署 SEFAUtil

1.  以 RTCUniversalServerAdmins 组成员的身份或利用[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述的必要用户权限登录安装了 Lync Server 命令行管理程序的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  SEFAUtil 工具只能在属于受信任应用程序池的一部分的计算机上运行。如有需要，请为您计划在其中运行 SEFAUtil 的前端池定义一个受信任应用程序池。在命令行中运行：
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  将 SEFAUtil 工具定义为受信任应用程序。在命令行中运行：
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    > [!NOTE]  
    > 如有需要，您可以使用其他端口。
    


5.  启用包含您的更改的拓扑。在命令行中运行：
    
        Enable-CsTopology

6.  在位于您在步骤 3 中创建的受信任应用程序池中的前端服务器上安装 Lync Server 2013 资源工具包工具。

7.  验证 SEFAUtil 工具是否正常运行，如下所示：
    
    1.  使用管理员权限从 Windows 命令提示符处运行该工具以在您的部署中显示用户的呼叫转接设置。
        
        > [!NOTE]  
		> 该工具位于 \Program Files\Microsoft Lync Server 2013\Reskit 下。
        
    
    2.  显示用户的呼叫转接设置。在命令行中运行：
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        将显示用户的呼叫转接设置。

