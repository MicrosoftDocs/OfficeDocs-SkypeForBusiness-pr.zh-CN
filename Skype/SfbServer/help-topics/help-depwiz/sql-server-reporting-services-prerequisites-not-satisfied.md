---
title: SQL Server Reporting Services（不满足先决条件）
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: 如果未在基础结构中部署监控服务器，则会看到此页。这表示尚未满足部署监控服务器报告的最低要求。
ms.openlocfilehash: 6c87bc180923442bfd1f32b6836a6d41256261d3fe3233b0f347071f6bf9e884
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304074"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services（不满足先决条件）

如果未在基础结构中部署监控服务器，则会看到此页。这表示尚未满足部署监控服务器报告的最低要求。

若要解决此问题，请确保监控服务器已加入域，已在拓扑生成器中定义监控服务器，并且已发布拓扑。 SQL Server Reporting Services还必须在 SQL Server 上可用，并作为一项功能安装到 SQL Server 上的监控服务器数据库中。

有关详细信息，请参阅 Install [Monitoring Reports in Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md)和[Deploying Monitoring。](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)