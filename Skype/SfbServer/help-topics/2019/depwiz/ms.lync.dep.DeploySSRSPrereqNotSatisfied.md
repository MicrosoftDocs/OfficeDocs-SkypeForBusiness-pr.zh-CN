---
title: SQL Server Reporting Services（不满足先决条件）
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
ROBOTS: NOINDEX, NOFOLLOW
description: 如果未在基础结构中部署监控服务器，则会看到此页。这表示尚未满足部署监控服务器报告的最低要求。
ms.openlocfilehash: df4dd71b0c66cb8bf2a8303638001e4f09b8e119
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843405"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services（不满足先决条件）

如果未在基础结构中部署监控服务器，则会看到此页。这表示尚未满足部署监控服务器报告的最低要求。

若要解决此问题，请确保监控服务器已加入域，已在拓扑生成器中定义监控服务器，并且已发布拓扑。 SQL Server Reporting Services还必须在客户端服务器上SQL Server，并作为一项功能安装到监控服务器上SQL Server。

有关详细信息，请参阅 Install [Monitoring Reports in Skype for Business Server](../../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)。