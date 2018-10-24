---
title: 查看受信任的应用程序信息
TOCTitle: 查看受信任的应用程序信息
ms:assetid: 7b916323-96fb-4308-bc95-c178de41a3d3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688103(v=OCS.15)
ms:contentKeyID: 49888476
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 查看受信任的应用程序信息

 

_**上一次修改主题：** 2015-03-30_

使用以下过程可查看 Lync Server 命令行管理程序中的 Lync Server 2013 命令行管理程序受信任应用程序信息。

## 使用 Lync Server 命令行管理程序 Cmdlet 查看受信任应用程序信息

您可以使用 Lync Server 命令行管理程序和 **Get-CsTrustedApplication** cmdlet 查看有关受信任应用程序的信息。可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 查看受信任应用程序

  - 若要查看所有受信任应用程序，请在 Lync Server 命令行管理程序中键入以下命令，然后按 Enter：
    
        Get-CsConferenceDisclaimer
    
    此命令将为每个受信任应用程序返回类似于下面的信息：
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True

有关详细信息，请参阅 [Get-CsTrustedApplication](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrustedApplication)。

