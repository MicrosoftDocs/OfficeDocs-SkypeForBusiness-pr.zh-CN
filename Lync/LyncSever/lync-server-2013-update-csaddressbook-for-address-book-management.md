---
title: 用于通讯簿管理的 Update-CsAddressBook
TOCTitle: 用于通讯簿管理的 Update-CsAddressBook
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg429695(v=OCS.15)
ms:contentKeyID: 49312022
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 用于通讯簿管理的 Update-CsAddressBook

 

_**上一次修改主题：** 2012-11-01_

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 Update-CsAddressBook cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

Update-CsAddressBook cmdlet 可替代 Office Communications Server 中的 **abserver.exe –syncNow** 命令。该 cmdlet 的用途是立即启动同步，而不是等到安排的时间才启动。第一个示例命令更新组织中的所有通讯簿。第二个示例命令仅更新与定义的服务器关联的通讯簿。

> [!NOTE]  
> 在 Lync Server 2013 中，Lync Server 用户复制程序将从 Active Directory 选取所做的更改并基于配置的时间间隔更新 Lync Server 用户数据库。Lync Server 用户复制程序还快速将更改传播到 RTCab 数据库，而无需管理员运行 Update-CSAddressBook。如果启用了通讯簿文件下载，则管理员只需要运行 Update-CSAddressBook。


例如：

    Update-CsAddressBook

   &nbsp;

    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com

有关完整命令的详细说明，请参阅主 Lync Server Windows PowerShell RTCCmdlets 参考中的以下内容。

## 另请参阅

#### 其他资源

[Update-CsAddressBook](https://docs.microsoft.com/en-us/powershell/module/skype/Update-CsAddressBook)

