---
title: 使用呼叫分析排查通话质量不佳的问题
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: 使用有关设备、网络和连接的按用户呼叫分析详细信息来排查用户Microsoft Teams和会议的问题。
ms.openlocfilehash: c6c95bd5fca4a5c1da84e5eedcc150242d4757adc03d309db66bbcb9fbbe0cef
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54327368"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>使用呼叫分析排查通话质量不佳的问题

本文介绍如何使用呼叫分析来排查单个用户的Microsoft Teams呼叫或会议质量不佳的问题（如果你是 Teams 管理员或 Teams 通信支持专家或工程师）。

## <a name="call-analytics-permissions"></a>调用分析权限

本文假定你已设置呼叫分析。 如果没有，请阅读为 Teams[设置呼叫Teams。](set-up-call-analytics.md)

## <a name="introduction-to-call-analytics"></a>调用分析简介

呼叫分析显示有关Teams帐户中每个用户的通话和Office 365的详细信息。 它包括有关设备、网络、连接和呼叫质量的信息 (其中任何一项都可能是导致呼叫或会议质量不佳) 。 如果上载建筑物、网站和租户信息，则每次呼叫和会议也会显示此信息。 使用呼叫分析帮助您找出用户通话或会议体验不佳的原因。

呼叫分析显示呼叫或会议的每一段 - 例如，从一个参与者到另一个参与者。 通过分析这些详细信息，Teams管理员可以隔离问题区域并确定质量不佳的根本原因。

作为Teams管理员，你可以完全访问每个用户的所有呼叫分析数据。 此外，还可以为Azure Active Directory人员分配其他角色。 若要详细了解这些角色，请阅读 [授予支持和支持人员的权限](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)。 请勿错过下面的[每个Teams角色的作用是什么？](#what-does-each-teams-support-role-do)

## <a name="where-to-find-per-user-call-analytics"></a>在何处查找按用户调用分析

若要查看用户的所有呼叫信息和数据，请转到 Teams[管理中心](https://admin.teams.microsoft.com)。 在 **"用户**"下，选择一个用户，然后打开&个人资料页上的"会议"选项卡。 可在此处找到该用户过去 30 天的所有呼叫和会议。

![所有分析用户数据的屏幕截图](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

若要获取有关给定会话的其他信息，包括详细的媒体和网络统计信息，请单击会话以查看详细信息。

![调用分析用户会话数据的屏幕截图](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

## <a name="what-does-each-teams-support-role-do"></a>每个支持Teams的作用是什么？

第 **1 层** Teams通信支持 (专家) 处理基本呼叫质量问题。 它们不调查会议问题。 相反，他们收集相关信息，然后上报给通信支持工程师。

第 **2** 层Teams通信 (工程师在详细的呼叫日志中) 信息，这些日志与 Teams支持专家隐藏。 下表列出了每个通信支持角色Teams的信息。

下表显示了每个通信支持角色可用的每用户信息。

|活动|信息|通信内容<br>支持 *专家* 参阅|通信内容<br>支持 *工程师* 看到|
|---|---|---|---|
|**呼叫**|呼叫者姓名|仅代理搜索的用户的名称。|用户名。|
||收件人姓名|显示为内部用户或外部用户。|收件人姓名。|
||主叫方电话号码|除最后三位数字外的全部电话号码都使用星号符号进行模糊处理。 例如，15552823 \* \* \* 。|除最后三位数字外的全部电话号码都使用星号符号进行模糊处理。 例如，15552823 \* \* \* 。|
||收件人电话号码|除最后三位数字外的全部电话号码都使用星号符号进行模糊处理。 例如，15552823 \* \* \* 。|除最后三位数字外的全部电话号码都使用星号符号进行模糊处理。 例如，15552823 \* \* \* 。|
||**呼叫详细信息** \>**"高级"** 选项卡|未显示信息。|显示的所有详细信息，例如设备名称、IP 地址、子网映射等。|
||**呼叫详细信息** \>**高级** \>**"调试"** 选项卡|未显示信息。|显示的所有详细信息，例如 DNS 后缀和 SSID。|
|**会议**|参与者姓名|仅代理搜索的用户的名称。 标识为内部用户或外部用户的其他参与者。|显示的所有名称。|
||参与者计数|参与者数。|参与者数。|
||会话详细信息|显示异常的会话详细信息。 只显示代理搜索的用户名。 标识为内部用户或外部用户的其他参与者。 电话号码的最后三位数字，用星号符号进行模糊处理。|显示会话详细信息。 显示用户名和会话详细信息。 电话号码的最后三位数字，用星号符号进行模糊处理。|
||||

## <a name="troubleshoot-user-call-quality-problems"></a>排查用户呼叫质量问题

1. 打开 Teams 管理 () ，然后使用 Teams <https://admin.teams.microsoft.com> 通信支持或Teams管理员凭据登录。

2. 在 **仪表板** 上的"用户 **搜索**"中，开始键入要排查其呼叫问题的用户的姓名或 SIP 地址，或选择"查看用户"以查看用户列表。

3. 从列表中选择用户。

4. 选择 **"呼叫** 历史记录"，然后选择要排除故障的呼叫或会议。

5. 选择" **高级"** 选项卡，然后查找指示通话质量不佳或连接问题的黄色和红色项目。

   在每个呼叫或会议会话详细信息中，次要问题以黄色显示。 如果某些内容为黄色，则超出正常范围，并且可能导致问题，但不太可能是问题的主要原因。 如果某些内容为红色，则这是一个严重问题，这很可能是导致此会话通话质量差的主要原因。

在极少数情况下，未收到音频会话的体验质量数据。 这通常是由丢弃的调用或与客户端的连接终止导致的。 发生这种情况时，会话分级 **不可用**。

对于具有 QoE (用户体验质量) 音频会话，下表描述了将会话限定为差 **的关键问题**。

|问题|区域|说明|
|---|---|---|
|呼叫设置|会话|错误代码 Ms-diag 20-29 指示调用设置失败。 用户无法加入呼叫或会议。|
|被分类为差的音频网络通话|会话|遇到数据包 (抖动、NMOS 降级、RTT 或隐藏比率等网络质量问题) 问题。|
|设备无法正常工作|Device|设备无法正常工作。 设备不正常运行的比率包括： <p> DeviceRenderNotFunctioningEventRatio >= 0.005 <br>  DeviceCaptureNotFunctioningEventRatio >= 0.005|
||||

## <a name="related-topics"></a>相关主题

[设置按用户调用分析](set-up-call-analytics.md)
