---
title: 删除公共区域电话联系对象
TOCTitle: 删除公共区域电话联系对象
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994087(v=OCS.15)
ms:contentKeyID: 52061174
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除公共区域电话联系对象

 

_**上一次修改主题：** 2013-02-20_

可能需要删除与公用区域电话关联的联系对象。例如，如果删除员工休息室的电话，则不再需要与该电话关联的联系对象。**Remove-CsCommonAreaPhone** cmdlet 提供了一种删除公用区域电话帐户的方法。运行此 cmdlet 时，将从 **Get-CsCommonAreaPhone** 返回的公用区域电话列表中删除该电话。此外，也将从 Active Directory 域服务中删除与该电话关联的联系对象。

使用 **Remove-CsCommonAreaPhone** 删除一个公用区域电话或所有具有共同元素（如显示名称或者国家/地区代码和区号）的公用区域电话。您可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。


## 删除指定公用区域电话

  - 以下命令删除 SIP 地址为 sip:mainlobby@litwareinc.com 的公用区域电话：
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

## 根据显示名称删除公用区域电话

  - 此命令删除显示名称包括字符串值“Building 14”的所有公用区域电话：
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

## 根据国家/地区代码和区号删除公用区域电话

  - 此命令删除美国（国家/地区代码为 1）和区号为 425 的所有公用区域电话：
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

有关详细信息，请参阅 [Remove-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCommonAreaPhone) cmdlet 的帮助主题。

## 另请参阅

#### 其他资源

[Get-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCommonAreaPhone)

