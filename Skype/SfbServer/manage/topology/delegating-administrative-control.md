---
title: 委派对项目的管理Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: ''
ms.openlocfilehash: 1ee1cdce6bae163ea51ebb73ac9b536e75b204a8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743418"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a>委派对项目的管理Skype for Business Server 

在Skype for Business Server中，通过使用基于角色的访问控制和 RBAC (功能，) 任务。 安装 Skype for Business Server时，会创建多个 RBAC 角色。 这些角色对应于 Active Directory 域服务中的通用安全组。 例如，RBAC 角色 CsHelpDesk 对应于在 Active Directory 域服务的用户容器中找到的 CsHelpDesk 组。 此外，每个 RBAC 角色都与一组 Skype for Business ServerWindows PowerShell cmdlet 相关联。   这些 cmdlet 表示已分配了给定 RBAC 角色的用户可以执行的任务。 例如，CsHelpDesk 角色已分配有 Lock-CsClientPin 和 UnlockCsClientPin cmdlet。 这意味着分配了 CsHelpDesk 角色的用户可以锁定和解锁用户 PIN 号码。 但是，尚未向 CsHelpDesk 角色分配New-CsVoicePolicy cmdlet。 这意味着分配了 CsHelpDesk 角色的用户无法创建新的语音策略。

## <a name="viewing-information-about-rbac-roles"></a>查看有关 RBAC 角色的信息

可以通过在命令行管理程序内运行以下命令来检索有关 RBAC 角色Skype for Business Server信息：

`Get-CsAdminRole`

请记住，RBAC 角色的标识 (例如 CsVoiceAdministrator) 具有到 Active Directory 域服务中的用户容器中找到的安全组的直接映射。

若要查看已分配给角色的 cmdlet 的列表，请使用以下类似命令：

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a>向用户分配 RBAC 角色

若要将 RBAC 角色分配给用户，必须将该用户添加到相应的 Active Directory 安全组。 例如，若要将 CsLocationAdministrator 角色分配给用户，必须将该用户添加到 CsLocationAdministrator 组。 这可以通过执行以下过程完成：

1. 使用有权修改 Active Directory 组成员身份的帐户登录到安装了 Active Directory 用户和计算机的计算机。
2. 单击 **"开始**"，单击"**所有** 程序"，单击 **"管理工具**"，然后单击 **"Active Directory 用户和计算机"。**
3. 在"Active Directory 用户和计算机"中，展开域的名称，然后单击"用户 **"** 容器。
4. 右键单击安全组 **CsLocationAdministrator**， **然后单击属性**。
5. 在"**属性**"对话框的"成员 **"** 选项卡上，单击"添加 **"。**
6. 在"选择用户、计算机、联系人或组"对话框中，键入要添加到组 (的用户的用户名或 显示名称 例如，Ken Myer) 在"输入要选择的对象名称"框中，然后单击"**确定**"。
7. 在“属性”对话框中，单击“确定”。

若要验证是否分配了 RBAC 角色，请使用 Get-CsAdminRoleAssignment cmdlet，向该 cmdlet 传递用户的 SamAccountName (Active Directory) 登录名。 例如，从命令行管理程序内部Skype for Business Server此命令：

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
