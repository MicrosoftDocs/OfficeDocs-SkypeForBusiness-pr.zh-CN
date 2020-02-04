---
title: 旧版合并
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: Web 会议外部 FQDN 允许外部用户加入本地会议。 输入旧版 Edge 服务器的 web 会议外部接口的完全限定的域名（FQDN）。
ms.openlocfilehash: 1f2a1e9ca3d3ca20b7b0fe6832a0e394d7fac5ce
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41688335"
---
# <a name="legacy-merge"></a>旧版合并

**Web 会议外部 FQDN**允许外部用户加入本地会议。 输入旧版 Edge 服务器的 web 会议外部接口的完全限定的域名（FQDN）。

**443**的**外部 Web 会议外部端口**值是为会议客户端配置的默认传输控制协议（TCP）会话初始协议（SIP）端口。 如果未使用默认值，请更新 "**外部 Web 会议外部端口**" 值。

如果计划将此 edge 服务器用于联盟，请选中 "**此边缘池用于联盟和公用 IM 连接**" 复选框。 如果您部署了多个边缘服务器，则仅为联盟启用其中一个。 如果未选中此框，并且你稍后决定要启用联盟，则必须再次运行拓扑生成器合并向导，并发布拓扑。 有关详细信息，请参阅[第4阶段：合并拓扑](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx)。


