---
title: 最佳做法分析器的组成员身份和用户权限要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9561736fc6dce1649d0a3dd29e15a7d88500a38
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a>Lync Server 2013 中的最佳做法分析器的组成员身份和用户权限要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-21_

若要成功运行最佳做法分析器，用于登录的用户帐户必须是本地计算机上管理员组的成员。 此外，若要扫描你的环境，用户帐户必须是以下组的成员：

  - **域管理员**   枚举 Active Directory 域服务信息并调用域控制器和全局编录服务器上的 Windows Management Instrumentation （WMI）提供程序。

  - ****   每个 Lync server 2013 内部计算机和每台边缘服务器上需要的管理员调用 Windows 管理规范（WMI）提供程序和访问注册表。

  - **RTCUniversalReadOnlyAdmins**   已满或已委派只读 Lync Server 2013 管理权限。

  - **Exchange 仅查看管理员**   完全查看或委派 exchange 仅查看 Microsoft Exchange 组织的管理员。

如果你的用户帐户没有足够的用户权限，你有两个选项：

  - 在命令提示符处，使用**runas**命令在具有足够用户权限的帐户下运行该工具。 语法如下所示：
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - 在 "**连接到 Active Directory** " 页面上，设置计划用于运行最佳做法分析器的帐户的凭据。 单击 "**显示高级登录选项**"。 你可以输入三个帐户：一个用于连接到 Active Directory 域服务，一个用于连接到 Lync Server 2013 Edge 服务器，另一个用于连接到 Exchange 服务器。 如果未指定任何这些帐户，则使用用于登录和运行最佳做法分析器的用户帐户。

</div>

<span> </span>

</div>

</div>

</div>

