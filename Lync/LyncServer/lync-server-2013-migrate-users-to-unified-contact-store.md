---
title: Lync Server 2013：将用户迁移到统一联系人存储
TOCTitle: 将用户迁移到统一联系人存储
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204737(v=OCS.15)
ms:contentKeyID: 49312236
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中将用户迁移到统一联系人存储

 

_**上一次修改主题：** 2012-10-15_

当用户处于以下情况时，会自动将用户的联系人迁移到 Exchange 2013 服务器：

  - 为其分配了将 UcsAllowed 设置为 True 的用户服务策略。

  - 为其设置了 Exchange 2013 邮箱并且该用户至少已登录该邮箱一次。

  - 使用 Lync 2013 富客户端登录。

如果用户使用 Lync 2010 或早期客户端登录，或者用户未连接至 Exchange 2013 服务器，将忽略用户服务策略并且用户的联系人将保留在 Lync Server 中。

您可以通过以下任一方法来确定是否已迁移用户的联系人：

  - 在客户端计算机上检查以下注册表项：
    
    HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\\<SIP URL\>\\UCS
    
    如果用户的联系人存储在 Exchange 2013 中，则此注册表项包含的 InUCSMode 的值为 2165。

  - 运行 **Test-CsUnifiedContactStore** cmdlet。在 Lync Server 命令行管理程序命令行中，键入：
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    如果 **Test-CsUnifiedContactStore** 成功，表明用户的联系人已迁移到统一联系人存储中。

