---
title: 分配会议策略以支持匿名用户
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 你可以通过配置会议策略来控制哪些人可以邀请匿名用户，并将该会议策略应用于特定用户。
ms.openlocfilehash: b5427ec96d3593cf87656f562acf0afc183b92d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818413"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>在 Skype for Business 服务器中分配会议策略以支持匿名用户 


默认情况下，将阻止所有用户邀请匿名用户参与会议。 你可以通过配置会议策略来控制哪些人可以邀请匿名用户，并将该会议策略应用于特定用户。 有关如何配置会议策略以支持匿名用户的详细信息，请参阅[在 skype For Business 服务器中创建会议策略](../../conferencing/create-policies.md)和[管理对 Skype for business 服务器的联盟和外部访问](../managing-federation-and-external-access.md)。

使用此部分中的过程将已创建的会议策略应用于一个或多个用户或用户组。

> [!NOTE]  
> 除了配置和应用策略以允许用户邀请匿名用户之外，还必须为你的组织启用匿名用户支持。 有关详细信息，请参阅[在 Skype For Business 服务器中配置用于控制公共用户访问的策略](../external-access-policies/configure-policies-to-control-public-user-access.md)。


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>配置匿名参与会议的用户策略

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中，单击 "**会议**"，然后执行下列操作之一：
    
    1.  若要创建新的用户策略，请单击 "**新建**"，然后单击 "**用户策略**"。 在 "**名称**" 字段中创建一个唯一名称，用于指示用户策略所涉及的内容（例如， **EnableAnonymous**适用于启用与匿名用户的通信的用户策略）。
    
    2.  若要配置现有用户策略，请单击表中列出的相应策略，单击 "**编辑**"，然后单击 "**显示详细信息**"。

4.  在 "**会议策略**" 对话框中，选中 "**允许参与者邀请匿名用户**" 复选框。

5.  单击“**提交**”。

6.  在左侧导航栏中，单击 "**用户**"，搜索要配置的用户帐户。

7.  在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。

8.  在 "**会议策略**" 下的 "**编辑 Skype for Business 服务器" 用户**中，选择包含要应用于此用户的匿名用户访问配置的用户策略。  

    > [!NOTE]  
    > " <STRONG> &lt;自动&gt; </STRONG>设置" 应用默认服务器安装设置，并由服务器自动应用。


若要使用户能够邀请匿名用户加入会议，还必须在组织中启用匿名用户支持。 有关详细信息，请参阅[在 Skype For Business 服务器中配置用于控制公共用户访问的策略](../external-access-policies/configure-policies-to-control-public-user-access.md)。

