---
title: 将 Lync Server 2010 会议目录移动到 Lync Server 2013
TOCTitle: 移动会议目录
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62388646
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 移动会议目录

 

_**上一次修改主题：** 2016-12-08_

在停用池之前，必须对 Lync Server 2010 池中的每个会议目录执行以下过程。

## 将会议目录移到 Lync Server 2013

1.  打开 Lync Server 命令行管理程序。

2.  若要获取组织中会议目录的标识，请运行以下命令：
    
        Get-CsConferenceDirectory
    
    上述命令返回组织中的所有会议目录。因此，您可能希望将结果限制为要停用的池。例如，如果正停用完全限定的域名 (FQDN) 为 pool01.contoso.net 的池，请使用此命令将返回的数据限制为该池中的会议目录：
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    该命令仅返回其中 ServiceID 属性包含 FQDN pool01.contoso.net 的会议目录。

3.  若要移动会议目录，请对池中的每个会议目录运行以下命令：
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    例如，要移动会议目录 3，请使用此命令并指定 Lync Server 2013 池作为 TargetPool：
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    如果希望移动某个池中的所有会议目录，请使用以下类似命令：
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

有关停用 Lync 2010 池的完整分步说明，请参阅文档“卸载 Microsoft Lync Server 2010 和删除服务器角色”（可以从以下位置进行下载：[http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)）。

移动会议目录时，您可能会遇到以下错误：

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

当 Lync Server 命令行管理程序 需要更新的一组 Active Directory 权限以便完成某项任务时，通常会发生此错误。要解决该问题，请关闭命令行管理程序的当前实例，然后打开命令行管理程序的新实例并重新运行该命令以移动会议目录。

