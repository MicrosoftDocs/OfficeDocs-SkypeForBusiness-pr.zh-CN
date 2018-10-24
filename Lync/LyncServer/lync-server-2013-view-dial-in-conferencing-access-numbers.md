---
title: 查看拨入会议访问数
TOCTitle: 查看拨入会议访问数
ms:assetid: 41a7dfb4-0c89-4650-b61b-0e1bf875c62b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688037(v=OCS.15)
ms:contentKeyID: 49888394
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 查看拨入会议访问数

 

_**上一次修改主题：** 2013-02-23_

在 Lync Server 2013 控制面板中，为用户提供拨入访问号码，以便其能够从外部加入会议。

## 查看拨入访问号码

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“会议”，然后单击“拨入访问号码”。

4.  在“拨入访问号码”页上，单击要查看的访问号码。

5.  在“编辑”中，选中“显示详细信息...”复选框。

## 通过使用 Lync Server PowerShell Cmdlet 查看电话拨入式会议访问号码

还可以使用 Lync Server PowerShell 和 Get-CsDialInConferencingAccessNumber cmdlet 查看电话拨入式会议访问号码。此 cmdlet 可从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 查看 SIP 中继配置信息

  - 若要查看有关电话拨入式会议访问号码的信息，请在 Lync Server 命令行管理程序中键入下列命令，然后按 Enter：
    
        Get-CsDialInConferencingAccessNumber
    
    这将返回与以下内容类似的信息：
    
        Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                             CN=Application Contacts,CN=RTCService=Services,
                             CN=Configuration,DC=litwareinc,DC=com
        PrimaryUri         : sip:testnumber@litwareinc.com
        DisplayName        : Test
        DisplayNumber      : 1-425-555-1019
        LineUri            : tel:+14255551019
        PrimaryLanguage    : en-US
        SecondaryLanguages : {}
        Pool               : atl-cs-001.litwareinc.com
        HostingProvider    :
        Regions            : {US}

有关详细信息，请参阅 [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsDialInConferencingAccessNumber) cmdlet 的帮助主题。

