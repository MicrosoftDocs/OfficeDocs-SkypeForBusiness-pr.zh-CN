---
title: 查看公共区域电话信息
TOCTitle: 查看公共区域电话信息
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994081(v=OCS.15)
ms:contentKeyID: 52061163
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 查看公共区域电话信息

 

_**上一次修改主题：** 2013-02-20_

您可以使用 **Get-CsCommonAreaPhone** cmdlet 查看有关配置为在组织中使用的公用区域电话的信息。使用此 cmdlet 时无需带任何参数，它返回有关您的所有公用区域电话的信息。可选参数为您提供了筛选信息的不同方法，例如，可以返回在指定组织单位 (OU) 中具有联系对象的所有公用区域电话，或位于指定建筑物的所有联系对象。有关 **Get-CsCommonAreaPhone** 参数的详细信息，请参阅 [Get-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCommonAreaPhone)。

从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行 **Get-CsCommonAreaPhone**。


## 查看有关您的所有公用区域电话的信息

  - 若要查看有关您的所有公用区域电话的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 Enter：
    
        Get-CsCommonAreaPhone
    
    您将收到如下信息：
    
        Identity           : CN=Building 14 Lobby,OU=Redmond,
                             DC=litwareinc,DC=com
        RegistrarPool      : atl-cs-001.litwareinc.com
        Enabled            : True
        SipAddress         : sip:4714e34b-9781-421d-b07a-
                             52056b5b4a56@litwareinc.com
        ClientPolicy       :
        PinPolicy          :
        VoicePolicy        :
        MobilityPolicy     :
        GroupChatPolicy    :
        ConferencingPolicy :
        LineURI            : tel:+14255550712
        DisplayNumber      : 1-425-555-0712
        DisplayName        : Building 14 Lobby
        Description        :
        ExUmEnabled        : False

有关详细信息，请参阅 [Get-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCommonAreaPhone) cmdlet 的帮助主题。

