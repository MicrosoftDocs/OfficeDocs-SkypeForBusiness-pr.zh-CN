---
title: SQL Server Reporting Services（不满足先决条件）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 2c5f58751d03d5c482bd3b9113b764ffe626cec6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823446"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services（不满足先决条件）

如果未在基础结构中部署监控服务器，则会看到此页。这表示尚未满足部署监控服务器报告的最低要求。

若要解决此问题，请确保你已将监视服务器加入到域中，该服务器已在拓扑生成器中定义，并且拓扑已发布。 SQL server Reporting Services 还必须在 SQL Server 上可用，并作为功能安装到 SQL Server 上的监视服务器数据库中。

有关详细信息，请参阅[在 Skype For Business Server 2015 中安装监视报告](../../deploy/deploy-monitoring/install-monitoring-reports.md)和[部署监视](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)。


