---
title: 通讯簿服务器 Cmdlet
TOCTitle: 通讯簿服务器 Cmdlet
ms:assetid: 33da45da-3c57-4d04-9679-f0e5a0cfd37e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg415643(v=OCS.15)
ms:contentKeyID: 49312447
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 通讯簿服务器 Cmdlet

 

_**上一次修改主题：** 2016-12-08_

通讯簿服务器是 Active Directory 域服务与 Microsoft Lync Server 2013 之间的中介。通讯簿服务器可确保 Lync Server 2013 中存储的用户信息与 Active Directory 中存储的用户信息同步。这是通过定期将通讯簿文件与用户数据库中存储的信息同步来实现的。而 Lync Server 中则包括许多用于管理通讯簿服务器的 cmdlet。

## 通讯簿服务器 Cmdlet

无法在 Lync Server 控制面板中配置通讯簿服务器设置。Windows PowerShell 是用于管理这些设置的主要工具。以下是与管理通讯簿服务器直接相关的 cmdlet 列表：

**通讯簿服务器**

  -   
    [Get-CsAddressBookConfiguration](get-csaddressbookconfiguration.md)

  -   
    [New-CsAddressBookConfiguration](New-CsAddressBookConfiguration.md)

  -   
    [Remove-CsAddressBookConfiguration](remove-csaddressbookconfiguration.md)

  -   
    [Set-CsAddressBookConfiguration](set-csaddressbookconfiguration.md)

<!-- end list -->

  -   
    [Update-CsAddressBook](update-csaddressbook.md)

  -   
    [Debug-CsAddressBookReplication](debug-csaddressbookreplication.md)

<!-- end list -->

  -   
    [Test-CsAddressBookService](test-csaddressbookservice.md)

  -   
    [Test-CsAddressBookWebQuery](test-csaddressbookwebquery.md)

## 另请参阅

#### 其他资源

[Lync Server PowerShell 博客](http://go.microsoft.com/fwlink/?linkid=203150%26clcid=0x804)

