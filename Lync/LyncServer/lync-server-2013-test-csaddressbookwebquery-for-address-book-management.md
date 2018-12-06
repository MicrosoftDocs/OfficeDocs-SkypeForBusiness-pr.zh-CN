---
title: 用于通讯簿管理的 Test-CsAddressBookWebQuery
TOCTitle: 用于通讯簿管理的 Test-CsAddressBookWebQuery
ms:assetid: 977a9c1f-5f4e-4539-9a26-8748b61a57d8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg429716(v=OCS.15)
ms:contentKeyID: 49313670
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 用于通讯簿管理的 Test-CsAddressBookWebQuery

 

_**上一次修改主题：** 2012-11-01_

谁能运行此 cmdlet：默认情况下，以下各组的成员有权运行 Test-CsAddressBookWebQuery cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

与 Test-CsAddressBookService 综合事务类似，Test-CsAddressBookWebQuery 对通讯簿 Web 查询执行查询以确保其正常运行。该 cmdlet 将连接到 Web 票证身份验证，并提供在 –UserCredential 中指定的凭据。如果通过身份验证，该 cmdlet 会提供 –TargetSipAddress 信息。如果该 cmdlet 能够检索到有关联系人的信息，则应报告成功。

例如：

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

有关完整命令的详细说明，请参阅主 Lync Server Windows PowerShell RTCCmdlets 参考中的以下内容。

## 另请参阅

#### 其他资源

[Test-CsAddressBookWebQuery](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsAddressBookWebQuery)

