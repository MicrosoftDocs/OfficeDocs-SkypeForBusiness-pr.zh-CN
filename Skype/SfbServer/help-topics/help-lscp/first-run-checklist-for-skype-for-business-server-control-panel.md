---
title: Skype for Business Server 控制面板的首次运行清单
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
description: 欢迎使用 Skype for Business Server 控制面板，这是用于管理 Skype for Business Server 的基于 Web 的用户界面。 可以使用控制面板执行之前版本中使用 Microsoft 管理控制台执行的管理任务类型。
ms.openlocfilehash: 74c1d4ae7b9ed65932acf5b8491a2cd00c67831c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804892"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Skype for Business Server 控制面板的首次运行清单

欢迎使用 Skype for Business Server 控制面板，这是用于管理 Skype for Business Server 的基于 Web 的用户界面。 可以使用控制面板执行之前版本中使用 Microsoft 管理控制台执行的管理任务类型。

我们强烈建议你在部署 Skype for Business Server 后执行许多重要任务。 其中某些任务是初始配置步骤，您可能已在部署过程中执行过，而另一些任务是对您在部署过程中配置的设置或默认设置的细化或修改。 本主题中介绍的其他任务可验证您在部署过程中所做的配置。

> [!NOTE]
> 在执行下表中的任务之前，请确保使用正确的用户权限、权限和角色进行登录，如"基于角色的访问控制"主题的"角色和作用域"[部分所述。](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)

## <a name="first-run-checklist"></a>首次运行检查表

强烈建议您查看本主题中引用的任务，然后执行组织中 Lync Server 部署的适当过程。

|**任务**|**控制面板组**|**文档**|
|:-----|:-----|:-----|
|验证在拓扑中安装的服务是否按预期运行。  <br/> |**拓扑** <br/> |[查看有关服务的详细信息](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|为用户启用 Skype for Business Server。 （可选）如果从早期版本迁移，将用户移动到 Skype for Business Server。  <br/> |**用户** <br/> |[管理用户](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|如果已部署或要部署企业语音，请配置 SIP 中继连接以启用与公用电话交换网 (PSTN) 的连接。  <br/> |**语音路由** <br/> |[配置中继和转换规则](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|如果已部署企业语音，请验证企业语音路由设置。  <br/> |**语音路由** <br/> |[测试语音路由](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|如果已部署存档服务器，请验证存档策略和设置是否满足组织的合规性要求。  <br/> |**监控和存档** <br/> |[管理存档](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|如果已部署监控服务器，请查看监控服务器报告以查看使用情况和诊断信息。  <br/> |**主页** <br/> |[在 Skype for Business Server 2015 中管理运行状况和监控](../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |


