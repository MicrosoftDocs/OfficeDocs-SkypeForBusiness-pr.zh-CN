---
title: 委派 Skype for Business 服务器的管理控制权
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 1775fc4f02b7efa9ec26b962154f0aa90b59b296
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279205"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a>委派 Skype for Business 服务器的管理控制权 

在 Skype for Business 服务器中, 使用基于角色的访问控制 (RBAC) 功能将管理任务委派给用户。 安装 Skype for Business 服务器时, 将为你创建许多 RBAC 角色。 这些角色对应 Active Directory 域服务中的通用安全组。 例如, RBAC 角色 CsHelpDesk 对应于 Active Directory 域服务中的用户容器内找到的 CsHelpDesk 组。 此外, 每个 RBAC 角色都与一组 Skype for Business 服务器 Windows PowerShell cmdlet 相关联。 这些 cmdlet 表示分配了给定的 RBAC 角色的用户可以执行的任务。 例如, 已向 CsHelpDesk 角色分配了 Lock CsClientPin 和 UnlockCsClientPin cmdlet。 这意味着分配了 CsHelpDesk 角色的用户可以锁定和解锁用户 PIN 码。 但是, 尚未向 CsHelpDesk 角色分配 CsVoicePolicy cmdlet。 这意味着分配了 CsHelpDesk 角色的用户无法创建新的语音策略。

## <a name="viewing-information-about-rbac-roles"></a>查看有关 RBAC 角色的信息

通过在 Skype for Business Server Management Shell 中运行以下命令, 你可以检索有关你的 RBAC 角色的基本信息:

`Get-CsAdminRole`

请记住, RBAC 角色的标识 (例如, CsVoiceAdministrator) 与 Active Directory 域服务中的用户容器中找到的安全组有直接映射。

若要查看已分配给某个角色的 cmdlet 的列表, 请使用类似下面的命令:

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a>向用户分配 RBAC 角色

若要向用户分配 RBAC 角色, 必须将该用户添加到相应的 Active Directory 安全组。 例如, 若要将 CsLocationAdministrator 角色分配给用户, 必须将该用户添加到 CsLocationAdministrator 组。 可通过执行以下过程来执行此操作:

1. 使用有权修改 Active Directory 组成员身份的帐户, 登录到已安装 Active Directory 用户和计算机的计算机。
2. 单击 "**开始**", 单击 "**所有程序**", 单击 "**管理工具**", 然后单击 " **Active Directory 用户和计算机**"。
3. 在 "Active Directory 用户和计算机" 中, 展开您的域的名称, 然后单击 "**用户**" 容器。
4. 右键单击安全组 " **CsLocationAdministrator**", 然后单击 "**属性**"。
5. 在 "**属性**" 对话框中的 "**成员**" 选项卡上, 单击 "**添加**"。
6. 在 "**选择用户、计算机、联系人或组**" 对话框中, 在 "**输入要选择的对象名称**" 框中键入要添加到组的用户的用户名或显示名称 (例如 Ken Myer), 然后单击 **"确定"**。
7. 在 "**属性**" 对话框中, 单击 **"确定"**。

若要验证 RBAC 角色是否已分配, 请使用 CsAdminRoleAssignment cmdlet 将 cmdlet 传递给用户的 SamAccountName (Active Directory 登录名称)。 例如, 在 Skype for Business Server Management Shell 中运行此命令:

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
