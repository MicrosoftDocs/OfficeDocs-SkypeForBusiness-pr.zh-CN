---
title: Lync Server 2013：委派 Lync Server 的管理控制权
description: Lync Server 2013：委派 Lync Server 的管理控制权。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegating administrative control of Lync Server 2013
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520951(v=OCS.15)
ms:contentKeyID: 48183418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8d3710af2d194a5aa4ebdd7291be2ee58176507
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567488"
---
# <a name="delegating-administrative-control-of-lync-server-2013"></a>委派 Lync Server 2013 的管理控制

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-22_

在 Lync Server 2013 中，管理任务通过使用新的基于角色的访问控制 (RBAC) 功能委派给用户。 当您安装 Lync Server 时，将为您创建许多 RBAC 角色。 这些角色对应于 Active Directory 域服务中的通用安全组。 例如，RBAC 角色 CsHelpDesk 对应于 Active Directory 域服务中的用户容器中找到的 CsHelpDesk 组。 此外，每个 RBAC 角色都与一组 Lync Server Windows PowerShell cmdlet 相关联。 这些 cmdlet 代表已分配了给定 RBAC 角色的用户可以执行的任务。 例如，已向 CsHelpDesk 角色分配了 Lock-CsClientPin 和 UnlockCsClientPin cmdlet。 这意味着分配了 CsHelpDesk 角色的用户可以锁定和解锁用户 PIN 号码。 但是，尚未向 CsHelpDesk 角色分配 New-CsVoicePolicy cmdlet。 这意味着分配了 CsHelpDesk 角色的用户不能创建新的语音策略。

<div>

## <a name="viewing-information-about-rbac-roles"></a>查看有关 RBAC 角色的信息

您可以通过在 Lync Server 命令行管理程序中运行以下命令来检索有关 RBAC 角色的基本信息：

    Get-CsAdminRole

请记住，RBAC 角色的标识 (例如，CsVoiceAdministrator) 与 Active Directory 域服务中的用户容器中的安全组的直接映射相匹配。

若要查看已分配给角色的 cmdlet 的列表，请使用类似如下的命令：

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a>向用户分配 RBAC 角色

若要向用户分配 RBAC 角色，您必须将该用户添加到相应的 Active Directory 安全组。 例如，若要将 CsLocationAdministrator 角色分配给用户，您必须将该用户添加到 CsLocationAdministrator 组。 为此，可以执行以下过程：

**将用户分配给安全组**

1.  使用有权修改 Active Directory 组成员身份的帐户登录到已安装 Active Directory 用户和计算机的计算机。

2.  依次单击 " **开始**"、" **所有程序**"、" **管理工具**" 和 " **Active Directory 用户和计算机**"。

3.  在 "Active Directory 用户和计算机" 中，展开您的域的名称，然后单击 " **用户** " 容器。

4.  右键单击安全组 " **CsLocationAdministrator**"，然后单击 " **属性**"。

5.  在 " **属性** " 对话框中的 " **成员** " 选项卡上，单击 " **添加**"。

6.  在 " **选择用户、计算机、联系人或组** " 对话框中，键入要添加到组的用户的用户名或显示名称 (例如， **Ken Myer**) 在 " **输入要选择的对象名称** " 框中，然后单击 **"确定"**。

7.  在“属性”**** 对话框中，单击“确定”****。

若要验证是否已分配 RBAC 角色，请使用 [CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) cmdlet，并将该 cmdlet 传递给用户的 SamAccountName (Active Directory 登录名) 。 例如，在 Lync Server 命令行管理程序中运行以下命令：

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>

