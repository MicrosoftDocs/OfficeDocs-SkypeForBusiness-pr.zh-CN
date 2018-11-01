---
title: 删除电话拨入式会议访问号码
TOCTitle: 删除电话拨入式会议访问号码
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg520956(v=OCS.15)
ms:contentKeyID: 49312141
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除电话拨入式会议访问号码

 

_**上一次修改主题：** 2013-02-23_

按照以下步骤删除电话拨入式会议访问号码。

## 删除电话拨入式会议访问号码

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到网络中部署了 Lync Server 2013 的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“会议”，然后单击“拨入访问号码”。

4.  在页面上，单击列表中要删除的电话拨入式号码，再单击“编辑”，然后单击“删除”。

5.  单击“确定”。

## 使用 Windows PowerShell Cmdlet 删除电话拨入式会议访问号码

也可以使用 Windows PowerShell 和 **Remove-CsDialInConferencingAccessNumber** cmdlet 删除电话拨入式会议访问号码。可从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 删除特定电话拨入式会议访问号码

  - 此命令可删除标识为 sip:RedmondDialInAccess@litwareinc.com 的电话拨入式会议访问号码：
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

## 删除分配给特定区域的所有电话拨入式会议访问号码

  - 此命令可删除与西北区域关联的所有电话拨入式会议访问号码：
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

## 删除基于主要语言的电话拨入式会议访问号码

  - 此命令可删除意大利语为主要语言的所有电话拨入式会议访问号码：
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

有关详细信息，请参阅 [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) cmdlet 的帮助主题。

