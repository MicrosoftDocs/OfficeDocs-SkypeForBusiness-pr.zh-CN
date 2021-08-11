---
title: Skype for Business Server 控制面板的首次运行清单
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
ROBOTS: NOINDEX, NOFOLLOW
description: 欢迎使用Skype for Business Server控制面板，该控制面板是基于 Web 的用户界面，用于管理 Skype for Business Server。 可以使用控制面板执行以前版本中使用 Microsoft 管理控制台执行的管理任务类型。
ms.openlocfilehash: 3fd383a13e9248c1c6cf5d4f272e58a74fa59f956b7fc7bdb494a789d1028ba6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307633"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Skype for Business Server 控制面板的首次运行清单

欢迎使用Skype for Business Server控制面板，该控制面板是基于 Web 的用户界面，用于管理 Skype for Business Server。 可以使用控制面板执行以前版本中使用 Microsoft 管理控制台执行的管理任务类型。

在部署部署后，我们强烈建议您执行一些Skype for Business Server。 其中某些任务是初始配置步骤，您可能已在部署过程中执行过，而另一些任务是对您在部署过程中配置的设置或默认设置的细化或修改。 本主题中介绍的其他任务可验证您在部署过程中所做的配置。

> [!NOTE]
> 在执行下表中的任务之前，请确保使用正确的用户权限和角色登录，如基于角色的访问控制主题的"角色和作用域"[部分所述。](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control)

## <a name="first-run-checklist"></a>首次运行检查表

强烈建议您查看本主题中提及的任务，然后执行适当的过程以在组织中进行部署。

|**任务**|**控制面板组**|**文档**|
|:-----|:-----|:-----|
|验证在拓扑中安装的服务是否按预期运行。  <br/> |**拓扑** <br/> |[查看有关服务的详细信息](/previous-versions/office/lync-server-2013/lync-server-2013-view-details-about-a-service) <br/> |
|为用户启用Skype for Business Server。 或者，如果从以前的版本迁移，将用户移动到Skype for Business Server。  <br/> |**用户** <br/> |[管理用户](/previous-versions/office/lync-server-2013/lync-server-2013-user-accounts-enabled-for-lync-server) <br/> |
|如果已部署或要部署企业语音，请配置 SIP 中继连接以启用与公用电话交换网 (PSTN) 的连接。  <br/> |**语音路由** <br/> |[配置中继和转换规则](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-trunks) <br/> |
|如果已部署企业语音，请验证企业语音路由设置。  <br/> |**语音路由** <br/> |[测试语音路由](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing) <br/> |
|如果已部署存档服务器，请验证存档策略和设置是否满足组织的合规性要求。  <br/> |**监控和存档** <br/> |[管理存档](/previous-versions/office/lync-server-2013/lync-server-2013-managing-archiving) <br/> |
|如果已部署监控服务器，请查看监控服务器报告以查看使用情况和诊断信息。  <br/> |**主页** <br/> |[在管理中管理运行状况Skype for Business Server](../../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |