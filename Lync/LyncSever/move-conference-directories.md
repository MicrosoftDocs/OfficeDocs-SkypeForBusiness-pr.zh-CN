---
title: 移动会议目录
TOCTitle: 移动会议目录
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204994(v=OCS.15)
ms:contentKeyID: 49313219
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 移动会议目录

 

_**上一次修改主题：** 2012-10-04_

在停用池之前，需要对 Office Communications Server 2007 R2 池中的每个会议目录执行以下过程。

## 将会议目录移到 Lync Server 2013

1.  打开 Lync Server 命令行管理程序。

2.  若要获取组织中会议目录的标识，请运行以下命令：
    
        Get-CsConferenceDirectory
    
    因为此 cmdlet 返回组织中的所有会议目录，所以您可能希望将结果限制为仅要停用的池。例如，如果要停用具有完全限定域名 (FQDN) pool01.contoso.net 的池：
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    此 cmdlet 返回其中服务 ID 包含 FQDN pool01.contoso.net 的所有会议目录。

3.  若要移动会议目录，请对池中的每个会议目录运行以下命令：
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    例如：
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

> [!NOTE]  
> 您可能会遇到下面显示的错误，此错误是由需要来自 Active Directory 的一组更新的权限的 Lync Server 命令行管理程序导致的。若要纠正此错误，请关闭当前窗口并打开一个新的 Lync Server 命令行管理程序，然后重新运行该命令。


![Move-CsConferenceDirectory 错误输出](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory 错误输出")

