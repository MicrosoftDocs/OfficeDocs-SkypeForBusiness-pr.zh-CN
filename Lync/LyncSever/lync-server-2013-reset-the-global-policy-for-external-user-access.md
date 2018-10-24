---
title: Lync Server 2013：重置外部用户访问的全局策略
TOCTitle: 重置外部用户访问的全局策略
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182545(v=OCS.15)
ms:contentKeyID: 49313437
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中重置外部用户访问的全局策略

 

_**上一次修改主题：** 2013-02-22_

无法完全删除全局策略。使用全局策略的“删除”选项只能将全局策略重置为默认设置，不包括对任何外部用户访问选项的支持。

## 将全局策略重置为默认设置

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“外部用户访问”，然后单击“外部访问策略”。

4.  在“外部访问策略”选项卡上，单击全局策略，再单击“编辑”，然后单击“删除”。

5.  当系统提示您确认删除时，单击“确定”。此时会在页面顶部显示一条消息，通知您已重置全局策略。

## 使用 Windows PowerShell Cmdlet 重置全局外部访问策略

还可使用 Windows PowerShell 和 Remove-CsExternalAccessPolicy cmdlet 重置全局外部访问策略。可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 重置全局外部访问策略

  - 此命令重置全局外部访问策略：
    
        Remove-CsExternalAccessPolicy -Identity "global"

有关详细信息，请参阅 [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet 的帮助主题。

