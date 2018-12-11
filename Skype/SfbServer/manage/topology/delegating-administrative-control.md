---
title: Skype 的管理控制权限委派业务服务器
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 6dbd254a96e4ffe961edc1a7d601870eb38b35db
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222896"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a>Skype 的管理控制权限委派业务服务器 

在业务服务器 Skype，管理任务将委派给用户通过使用基于角色的访问控制 (RBAC) 功能。 业务服务器安装 Skype 时，将为您创建多个 RBAC 角色。 这些角色对应 Active Directory 域服务中的通用安全组。 例如，RBAC 角色 CsHelpDesk 对应于 Active Directory 域服务中的用户容器中找到的 CsHelpDesk 组。 此外，每个 RBAC 角色相关联的 Skype 一组业务 Server Windows PowerShell cmdlet。 这些 cmdlet 表示由已分配的给定的 RBAC 角色的用户可以执行的任务。 例如，已分配 CsHelpDesk 角色 Lock-csclientpin 和 UnlockCsClientPin cmdlet。 这意味着已分配 CsHelpDesk 角色的用户可以锁定和解除锁定用户 PIN 号码。 但是，CsHelpDesk 角色尚未分配 New-csvoicepolicy cmdlet。 这意味着已分配 CsHelpDesk 角色的用户无法创建新的语音策略。

## <a name="viewing-information-about-rbac-roles"></a>查看有关 RBAC 角色的信息

可以通过为业务 Server Management Shell 中运行以下命令从 Skype 中的检索有关 RBAC 角色的基本信息：

`Get-CsAdminRole`

请记住，RBAC 角色 (例如，CsVoiceAdministrator) 的标识直接映射到 Active Directory 域服务中的用户容器中找到的安全组。

若要查看已分配给某个角色的 cmdlet 的列表，请使用类似如下的命令：

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a>将 RBAC 角色分配给用户

若要 RBAC 角色分配给用户，必须将该用户添加到相应的 Active Directory 安全组。 例如，若要将 CsLocationAdministrator 角色分配给用户，必须将该用户添加到 CsLocationAdministrator 组中。 可通过执行以下过程：

1. 使用 Active Directory 用户和计算机已安装的帐户有权修改的 Active Directory 组的成员身份，登录到计算机上。
2. 单击**开始**，单击**所有程序**，都单击**管理工具**，然后都单击**Active Directory 用户和计算机**。
3. 在 Active Directory 用户和计算机，展开您的域的名称，然后单击**用户**容器。
4. 右键单击安全组**CsLocationAdministrator**，，然后单击**属性**。
5. 在**属性**对话框中，在**成员**选项卡上，单击**添加**。
6. 在**选择用户、 计算机、 联系人或组**对话框中，键入用户名或要添加到组 (例如，Ken Myer) 中的**输入要选择的对象名称**框中，用户的显示名称，然后单击**确定**。
7. 在**属性**对话框中，单击**确定**。

若要验证已分配的 RBAC 角色，使用 Get-csadminroleassignment cmdlet，传递此 cmdlet 的用户的 SamAccountName （Active Directory 登录名）。 例如，运行 Business Server 命令行管理程序中 Skype 此命令：

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`