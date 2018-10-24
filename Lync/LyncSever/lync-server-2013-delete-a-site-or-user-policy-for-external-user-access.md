---
title: Lync Server 2013：删除外部用户访问的站点或用户策略
TOCTitle: 删除外部用户访问的站点或用户策略
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg521013(v=OCS.15)
ms:contentKeyID: 49313180
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中删除外部用户访问的站点或用户策略

 

_**上一次修改主题：** 2013-02-22_

可以在“外部访问策略”页上删除 Lync Server 控制面板中列出的任何站点或用户策略。删除全局策略时不会真正删除该策略，而只是将其重置为不支持任何外部用户访问选项的默认设置。有关重置全局策略的详细信息，请参阅[在 Lync Server 2013 中重置外部用户访问的全局策略](lync-server-2013-reset-the-global-policy-for-external-user-access.md)。

## 删除外部用户访问的站点或用户策略

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  单击“外部用户访问”，再单击“外部访问策略”。

4.  在“外部访问策略”选项卡上，单击要删除的站点或用户策略，再单击“编辑”，然后单击“删除”。

5.  当系统提示您确认删除时，单击“确定”。

## 使用 Windows PowerShell cmdlet 删除 PIN 策略

可以使用 Windows PowerShell 和 Remove-CsExternalAccessPolicy cmdlet 删除外部访问策略。此 cmdlet 可从 Lync Server 2013 命令行管理程序 或从 Windows PowerShell 的远程会话中运行。

## 删除特定外部访问策略

  - 此命令删除适用于 Redmond 站点的外部访问策略：
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

## 删除应用于每用户范围的所有外部访问策略

  - 此命令删除在每用户范围配置的所有外部访问策略：
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

## 删除已禁用外部用户访问的所有外部访问策略

  - 此命令删除已禁用外部用户访问的所有外部访问策略：
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

有关详细信息，请参阅 [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet 的帮助主题。

