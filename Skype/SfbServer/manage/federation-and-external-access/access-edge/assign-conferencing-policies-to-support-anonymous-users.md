---
title: 分配会议策略以支持匿名用户
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 您可以控制可以通过配置会议策略以支持匿名用户，并将该会议策略应用于特定用户邀请匿名用户。
ms.openlocfilehash: 62ff84b19fadbeaf0f26fa3e5869026254d28d1f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881125"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>分配会议策略以支持匿名用户在 Skype 业务服务器 


默认情况下阻止所有用户邀请匿名用户参加会议。 您可以控制可以通过配置会议策略以支持匿名用户，并将该会议策略应用于特定用户邀请匿名用户。 有关如何配置会议策略以支持匿名用户的详细信息，请参阅[Skype 业务服务器中的创建会议策略](../../conferencing/create-policies.md)和[管理联合身份验证和 Skype 业务服务器的外部访问](../managing-federation-and-external-access.md)。

使用本节中的过程，您已创建会议策略应用于一个或多个用户或用户组。

> [!NOTE]  
> 除了配置并应用允许用户邀请匿名用户的策略，还必须为您的组织中启用对匿名用户的支持。 有关详细信息，请参阅[配置策略以控制 Skype 业务服务器中的公共用户访问](../external-access-policies/configure-policies-to-control-public-user-access.md)。


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>配置匿名参与会议的用户策略

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**会议**，然后执行下列选项之一：
    
    1.  若要创建一个新用户策略，单击**新建**，然后单击**用户策略**。 在**名称**字段，该值指示用户策略 （例如， **EnableAnonymous**启用与匿名用户的通信用户策略） 的介绍中创建一个唯一的名称。
    
    2.  若要配置现有用户策略，单击表中列出的相应策略，单击**编辑**，然后单击**显示详细信息**。

4.  在**会议策略**对话框中，选择**允许参与者邀请匿名用户**复选框。

5.  单击“**提交**”。

6.  在左侧的导航栏中，单击**用户**，搜索要配置的用户帐户。

7.  在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。

8.  在**会议策略**下**的企业服务器用户编辑 Skype** ，选择您想要应用于此用户的匿名用户访问配置的用户策略。  

    > [!NOTE]  
    > <STRONG>&lt;自动&gt;</STRONG>设置应用默认服务器安装设置，并由服务器自动应用。


允许用户邀请匿名用户参加会议，您还必须在组织中启用对匿名用户的支持。 有关详细信息，请参阅[配置策略以控制 Skype 业务服务器中的公共用户访问](../external-access-policies/configure-policies-to-control-public-user-access.md)。

