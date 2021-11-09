---
title: 会议详细信息报告Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 摘要：了解会议详细信息报告中Skype for Business Server。
ms.openlocfilehash: a86124c05e0d35caef3f92c4ec43b561eb54938c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829986"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a>会议详细信息报告Skype for Business Server

**摘要：** 了解会议详细信息报告中用于Skype for Business Server。

会议详细信息报告提供有关参与会议的所有用户的详细信息。 例如，可以看到用户加入会议的日期和时间、用户离开会议的日期和时间，以及用于将该用户连接到会议的终结点的用户代理等信息。 还可以查看用户在每个会议角色中的角色信息 (例如演示者或与会者) 。 也许最重要的是，您可以快速了解哪些用户已成功加入和完成会议，哪些用户未能成功加入和完成会议。

## <a name="accessing-the-conference-detail-report"></a>访问会议详细信息报告

可以从以下报告访问会议详细信息报告：

- 呼叫 [允许控制报告](call-admission-control-report.md) (会议记录的详细信息指标进行) 

- 故障 [列表报告](failure-list-report.md) (会议指标列表) 

- 用户 [活动报告](call-diagnostic-reports-per-user.md) (单击"会议 URI"指标) 

从会议详细信息报告中，可以通过单击诊断报告 ([详细信息) 报告](diagnostic-report.md) 。

## <a name="filters"></a>筛选器

无。 您无法对会议详细信息报告进行筛选。

## <a name="metrics"></a>度量标准

下表列出了会议详细信息报告的"会议信息"部分提供的信息。

**会议信息指标**


| **名称**                 | **说明**                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| **会议 URI** <br/> | 分配给会议的 URI。 例如：  <br/> sip：kmyer@litwareinc.com;gruu;opaque=app：conf：focus：id：drg2y8v4  <br/> |
| **池 FQDN** <br/>      | 会话中涉及的注册器池或边缘服务器的完全限定域名。  <br/>                             |
| **开始时间** <br/>     | 会议开始的日期和时间。  <br/>                                                                          |
| **Organizer** <br/>      | 组织会议的用户的 SIP 地址。  <br/>                                                               |
| **结束时间** <br/>       | 会议结束的日期和时间。  <br/>                                                                            |

下表列出了会议详细信息报告的"会议参与"部分提供的信息。

**会议参与指标**

|**名称**|**说明**|
|:-----|:-----|
|**用户** <br/> |参与会议的用户的 SIP 地址。  <br/> |
|**角色** <br/> |会议参与者扮演的角色（例如“演示者”）。  <br/> |
|**连接性** <br/> |参与者的网络连接（通常为“来自内部”或“来自外部”）。  <br/> |
|**加入时间** <br/> |参与者加入会议的日期和时间。  <br/> |
|**离开时间** <br/> |参与者离开会议的日期和时间。  <br/> |
|**用户代理** <br/> |参与者终结点使用的软件的标识符。  <br/> |
|**诊断报告** <br/> |提供诊断和疑难解答信息。 包括失败的会话的 SIP 响应代码、诊断标头、会议加入时间以及诊断 ID。  <br/> |

下表列出了会议详细信息报告的"会议形式"部分提供的信息。

**会议形式指标**

|**名称**|**说明**|
|:-----|:-----|
|**用户** <br/> |参与会议的用户的 SIP 地址。  <br/> |
|**加入时间** <br/> |参与者加入会议的日期和时间。  <br/> |
|**离开时间** <br/> |参与者离开会议的日期和时间。  <br/> |
|**会议服务器 URI** <br/> |会议中使用的会议服务器的 URI。  <br/> |
|**诊断报告** <br/> |提供诊断和疑难解答信息。 包括失败的会话的 SIP 响应代码、诊断标头、会议加入时间以及诊断 ID。  <br/> |


