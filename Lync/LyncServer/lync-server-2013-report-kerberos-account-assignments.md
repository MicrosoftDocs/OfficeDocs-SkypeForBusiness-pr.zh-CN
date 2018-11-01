---
title: Lync Server 2013：报告 Kerberos 帐户分配
TOCTitle: 报告 Kerberos 帐户分配
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398343(v=OCS.15)
ms:contentKeyID: 49312842
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中报告 Kerberos 帐户分配

 

_**上一次修改主题：** 2012-01-16_

要成功完成此过程，应以 RTCUniversalServerAdmins 组成员的身份登录。

可以使用 **Get-CsKerberosAccountAssignment** cmdlet 来查询有关 Kerberos 身份验证帐户分配的信息和报告部署中的当前分配的相关信息。

## 查询某个站点的 Kerberos 身份验证帐户分配

1.  以 RtcUniversalServerAdmins 组成员的身份，登录到域中运行 Lync Server 2013 的计算机，或登录到安装了管理工具的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  从命令行运行下列命令之一：
    
      - 要查询组织中的所有 Kerberos 身份验证帐户分配并返回每一个的相关分配信息，请运行不带任何参数的 cmdlet：
        
            Get-CsKerberosAccountAssignment
    
      - 要查询部署中的所有 Kerberos 身份验证帐户分配并返回每一个的相关站点分配信息，请运行带有 Identity 参数的 cmdlet：
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        例如：
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - 要查询单个站点中的所有 Kerberos 身份验证帐户分配并返回每一个的相关分配信息，请运行带有 Filter 参数的 cmdlet：
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        例如：
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        > [!NOTE]  
		> 指定 Filter 参数的 *SiteName 将返回有关在站点标识符的任何位置包含指定的站点名称的所有站点（例如，在站点标识符中包含字符串 Redmond 的所有站点）的相关信息。
        

