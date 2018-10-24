---
title: 创建或修改公共区域电话联系对象
TOCTitle: 创建或修改公共区域电话联系对象
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994083(v=OCS.15)
ms:contentKeyID: 52061151
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 创建或修改公共区域电话联系对象

 

_**上一次修改主题：** 2013-02-20_

若要为您的所有公用区域电话创建 Active Directory 域服务联系对象，请使用 **New-CsCommonAreaPhone** cmdlet。此 cmdlet 可创建与公用区域电话配合使用的新联系对象，也可以将现有联系对象与新的公用区域电话关联。若要修改与公用区域电话相关联的联系对象的属性，请使用 **Set-CsCommonAreaPhone** cmdlet。**Set-CsCommonAreaPhone** 的可选参数使您能够更改项目，例如联系人的 Active Directory 显示名称或与电话关联的线路统一资源标识符 (URI)，以及启用或禁用用于与 Lync Server 一起使用的帐户。有关所有可用修改的详细信息，请参阅 [Set-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCommonAreaPhone) 中的“参数”一节。有关 **New-CsCommonAreaPhone** 参数的详细信息，请参阅 [New-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCommonAreaPhone)。

您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行这两个 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。


## 创建公用区域电话联系对象

  - 若要创建新的公用区域电话联系对象，请使用 **New-CsCommonAreaPhone** cmdlet。在创建联系对象时，您至少必须提供以下信息：
    
      - **LineUri**：分配给公用区域电话的电话号码。请注意，在指定电话号码时您必须使用 E.164 格式。
    
      - **RegistrarPool**：将承载联系对象的注册器池的完全限定域名 (FQDN)。
    
      - **OU**：将在其中创建联系对象的 Active Directory 容器的可分辨名称。
    
    我们还建议您提供 Active Directory 域服务显示名称。否则，您将需要使用 GUID 来指定电话 Identity。例如：
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

## 修改公用区域电话联系对象

  - 若要修改现有公用区域电话联系对象的属性，请使用 **Set-CsCommonAreaPhone** cmdlet。例如，此命令使用 DisplayName Lobby 为公用区域电话配置 SIP 地址：
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

有关详细信息，请参阅 [New-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCommonAreaPhone) cmdlet 和 [Set-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCommonAreaPhone) cmdlet 的帮助主题。

