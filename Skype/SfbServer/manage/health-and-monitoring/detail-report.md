---
title: Skype for Business 服务器中的会议详细报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: '摘要: 了解 Skype for Business 服务器中使用的会议详细信息报表。'
ms.openlocfilehash: 17337624c955dfa174f7b98772fdd836e82891d0
ms.sourcegitcommit: 6cbdcb8606044ad7ab49a4e3c828c2dc3d50fcc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/09/2019
ms.locfileid: "36271389"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a>Skype for Business 服务器中的会议详细报告

**摘要:** 了解 Skype for Business 服务器中使用的会议详细信息报表。

会议详细信息报告提供有关参与会议的所有用户的详细信息。例如，您可以查看用户加入会议的日期和时间、用户离开会议的日期和时间以及用于将该用户连接到会议的端点的用户代理等信息。还可以查看用户在每个会议中的角色的信息（例如，演示者或与会者）。可能最重要的是，您可以快速查看哪些用户成功加入和完成会议，哪些用户无法成功加入和完成会议。

## <a name="accessing-the-conference-detail-report"></a>访问会议详细信息报告

可从以下报告中访问会议详细信息报告：

- [Call Admission Control Report](call-admission-control-report.md)（通过单击会议的“详细信息”指标）

- [Failure List Report](failure-list-report.md)（通过单击“会议”指标）

- [User Activity Report](call-diagnostic-reports-per-user.md)（通过单击“会议 URI”指标）

从会议详细信息报告中，可通过单击“诊断报告(详细信息)”指标来访问 [Diagnostic Report](diagnostic-report.md)。

## <a name="filters"></a>筛选器

无。您无法筛选会议详细信息报告。

## <a name="metrics"></a>指标

下表列出了会议详细信息报告的“会议信息”部分提供的信息。

**会议信息指标**


| **名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。                 | **说明**                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| **会议 URI** <br/> | 分配给会议的 URI。例如：  <br/> sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4  <br/> |
| **池 FQDN** <br/>      | 会话中涉及的注册器池或边缘服务器的完全限定域名。  <br/>                             |
| **开始时间** <br/>     | 会议开始的日期和时间。  <br/>                                                                          |
| **组织者** <br/>      | 组织会议的用户的 SIP 地址。  <br/>                                                               |
| **结束时间** <br/>       | 会议结束的日期和时间。  <br/>                                                                            |

下表列出了会议详细信息报告的“会议参与”部分提供的信息。

**会议参与指标**

|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。|**说明**|
|:-----|:-----|
|**用户** <br/> |参与会议的用户的 SIP 地址。  <br/> |
|**角色** <br/> |会议参与者扮演的角色（例如“演示者”）。  <br/> |
|**连接** <br/> |参与者的网络连接（通常为“来自内部”或“来自外部”）。  <br/> |
|**加入时间** <br/> |参与者加入会议的日期和时间。  <br/> |
|**离开时间** <br/> |参与者离开会议的日期和时间。  <br/> |
|**用户代理** <br/> |参与者终结点使用的软件的标识符。  <br/> |
|**诊断报告** <br/> |提供诊断和故障排除信息。包括 SIP 响应代码、诊断标题、会议加入时间和失败会话的诊断 ID。  <br/> |

下表列出了会议详细信息报表的 "会议形式" 部分中提供的信息。

**会议形式指标**

|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。|**说明**|
|:-----|:-----|
|**用户** <br/> |参与会议的用户的 SIP 地址。  <br/> |
|**加入时间** <br/> |参与者加入会议的日期和时间。  <br/> |
|**离开时间** <br/> |参与者离开会议的日期和时间。  <br/> |
|**会议服务器 URI** <br/> |会议中使用的会议服务器的 URI。  <br/> |
|**诊断报告** <br/> |提供诊断和故障排除信息。包括 SIP 响应代码、诊断标题、会议加入时间和失败会话的诊断 ID。  <br/> |


