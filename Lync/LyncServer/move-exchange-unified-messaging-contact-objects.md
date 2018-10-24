---
title: 移动 Exchange 统一消息联系人对象
TOCTitle: 移动 Exchange 统一消息联系人对象
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49888376
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 移动 Exchange 统一消息联系人对象

 

_**上一次修改主题：** 2012-10-19_

若要将自动助理 (AA) 和订阅者访问 (SA) 联系对象迁移到新的 Lync Server 2013 部署，请先使用 **Get-CsExUmContact** 和 **Move-CsExUmContact** cmdlet 将这些对象从旧 Office Communications Server 2007 R2 部署移到新 Lync Server 2013 部署。然后在 Exchange Server 上，运行 **ExchUCUtil**Windows PowerShell 脚本，以便对新部署的 Lync 池执行下列操作：

  - 将其添加到统一消息 IP 网关。

  - 将其添加到统一消息智能寻线。

> [!NOTE]  
> 若要使用 <strong>Get-CsExUmContact</strong> 和 <strong>Move-CsExUmContact</strong> cmdlet，您必须是 RTCUniversalUserAdmins 组的成员，并且拥有存储联系对象的组织单位 (OU) 的 OU 权限。可以使用 <strong>Grant-OUPermission</strong> cmdlet 授予 OU 权限。


## 使用 Lync Server 命令行管理程序移动联系对象

1.  打开 Lync Server 命令行管理程序。

2.  对于在命令行向 Exchange UM 注册的每个池（其中，pool1.contoso.net 是 Office Communications Server 2007 R2 部署中的池，而 pool2.contoso.net 是 Lync Server 2013 部署中的池），请键入以下内容：
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    若要验证是否已移动联系对象，请运行 **Get-CsExumContact** cmdlet，并确认“RegistrarPool”现在指向新池。

## 运行 ExchUCUtil Windows PowerShell 脚本

1.  以具有 Exchange 组织管理员权限的用户身份登录到 Exchange UM 服务器。

2.  导航到 ExchUCUtil Windows PowerShell 脚本。
    
    在 Exchange 2007 中，ExchUCUtil.ps1 位于： **%Program Files%\\Microsoft\\Exchange Server\\Scripts\\ExchUCUtil.ps1**
    
    在 Exchange 2010 中，ExchUCUtil.ps1 位于： **%Program Files%\\Microsoft\\Exchange Server\\V14\\Scripts\\ExchUCUtil.ps1**

3.  如果 Exchange 部署在单个林中，请键入：
    
        exchucutil.ps1
    
    否则，如果 Exchange 部署在多个林中，则键入：
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    其中，*forest FQDN* 指定在其中部署 Lync Server 2013 的林。
    
    > [!IMPORTANT]
    > 运行 exchucutil.ps1 后，请确保重新启动“Lync Server 前端”服务 (rtcsrv.exe)。否则，Lync Server 2013 将无法在拓扑中检测统一消息。

