---
title: 分配会议策略以支持匿名用户
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 通过配置支持匿名用户的会议策略并将该会议策略应用于特定用户，可以控制能够邀请匿名用户的用户。
ms.openlocfilehash: 57d100569722cbe89811d15eb9fbe04e5d375711
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817452"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>分配会议策略以支持 Skype for Business Server 中的匿名用户 


默认情况下，禁止所有用户邀请匿名用户参加会议。 通过配置支持匿名用户的会议策略并将该会议策略应用于特定用户，可以控制能够邀请匿名用户的用户。 若要详细了解如何配置会议策略以支持匿名用户，请参阅在 [Skype for Business Server](../../conferencing/create-policies.md) 中创建会议策略以及管理对 Skype for Business Server 的联盟和 [外部访问](../managing-federation-and-external-access.md)。

使用本节中的过程可将已创建的会议策略应用于一个或多个用户或用户组。

> [!NOTE]  
> 除了配置和应用策略以允许用户邀请匿名用户之外，还必须为组织启用对匿名用户的支持。 有关详细信息，请参阅 [配置策略以控制 Skype for Business Server 中的公共用户访问](../external-access-policies/configure-policies-to-control-public-user-access.md)。


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>为匿名参与会议配置用户策略

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。 

3.  在左侧导航栏中，单击“会议”，然后执行下列操作之一：
    
    1.  要创建新的用户策略，请单击“新建”，然后单击“用户策略”。在“名称”字段中，创建一个唯一的名称以指示用户策略的作用范围（例如，**EnableAnonymous** 代表允许与匿名用户进行通信的用户策略）。
    
    2.  要配置现有用户策略，请单击表中列出的相应策略，再单击“编辑”，然后单击“显示详细信息”。

4.  在“会议策略”对话框中，选中“允许参与者邀请匿名用户”复选框。

5.  单击“提交”。

6.  在左侧导航栏中，单击“用户”，搜索要配置的用户帐户。

7.  在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”，然后单击“显示详细信息”。

8.  在 **"编辑会议** 策略下的 Skype for Business Server 用户"中，选择具有要应用于此用户的匿名用户访问配置的用户策略。  

    > [!NOTE]  
    > 自动设置应用默认服务器安装设置，并自动由服务器应用。 <STRONG> &lt; &gt; </STRONG>


要允许用户邀请匿名用户参加会议，还必须在组织中启用匿名用户支持。 有关详细信息，请参阅 [配置策略以控制 Skype for Business Server 中的公共用户访问](../external-access-policies/configure-policies-to-control-public-user-access.md)。

