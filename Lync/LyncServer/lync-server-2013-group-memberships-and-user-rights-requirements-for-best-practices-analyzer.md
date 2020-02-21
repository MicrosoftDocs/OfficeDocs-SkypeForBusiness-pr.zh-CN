---
title: 最佳实践分析工具的组成员身份和用户权限要求
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
ms.openlocfilehash: 81dbf72e995291731c95749c3b1daecbf454190a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a>Lync Server 2013 中最佳实践分析工具的组成员身份和用户权限要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-21_

要成功运行最佳做法分析器，您用于登录的用户帐户必须是本地计算机上 Administrators 组的成员。另外，要扫描您的环境，用户帐户必须是下列组的成员：

  - **域管理员**   枚举 Active Directory 域服务信息，并调用域控制器和全局编录服务器上的 Windows Management Instrumentation （WMI）提供程序。

  - ****   每个 Lync server 2013 内部计算机和每台边缘服务器上所需的管理员调用 Windows Management Instrumentation （WMI）提供程序并访问注册表。

  - **RTCUniversalReadOnlyAdmins**   已满或委派只读 Lync Server 2013 管理权限。

  - **Exchange 仅查看**   Microsoft Exchange 组织上的管理员完全或委派 exchange 仅查看管理员。

如果您的用户帐户没有充分的用户权限，则您有两个选项：

  - 在命令提示符下，使用 **runas** 命令在具有充分用户权限的帐户下运行该工具。 语法如下所示：
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - 在“连接到 Active Directory”**** 页面上，为您计划用于运行最佳做法分析器的帐户设置凭据。 单击“显示高级登录选项”****。 您可以输入三个帐户：一个用于连接到 Active Directory 域服务，一个用于连接到 Lync Server 2013 边缘服务器，另一个用于连接到 Exchange 服务器。 如果您不指定这些任何帐户，则使用用于登录和运行最佳做法分析器的帐户。

</div>

<span> </span>

</div>

</div>

</div>

