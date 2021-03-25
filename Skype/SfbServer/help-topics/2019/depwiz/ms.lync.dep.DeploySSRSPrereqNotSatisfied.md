---
title: SQL Server Reporting Services（不满足先决条件）
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
ROBOTS: NOINDEX, NOFOLLOW
description: 如果未在基础结构中部署监控服务器，则会看到此页。这表示尚未满足部署监控服务器报告的最低要求。
ms.openlocfilehash: 657c1b203dd5d01fedde9ad0c5b08c6775f4bd4e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118901"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services（不满足先决条件）

如果未在基础结构中部署监控服务器，则会看到此页。这表示尚未满足部署监控服务器报告的最低要求。

若要解决此问题，请确保监控服务器已加入域，已在拓扑生成器中定义监控服务器，并且已发布拓扑。 SQL Server Reporting Services 还必须在 SQL Server 上可用，并作为一项功能安装到 SQL Server 上的监控服务器数据库中。

有关详细信息，请参阅 Install [Monitoring Reports in Skype for Business Server](../../../deploy/deploy-monitoring/install-monitoring-reports.md)和[Deploying Monitoring。](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)