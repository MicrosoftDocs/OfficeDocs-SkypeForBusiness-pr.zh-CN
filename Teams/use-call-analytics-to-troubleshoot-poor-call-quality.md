---
title: 使用通话分析来排查通话质量不良问题
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: 使用有关设备、网络和连接的按用户呼叫分析详细信息来排查 Microsoft Teams 呼叫和会议的用户问题。
ms.openlocfilehash: 38636d911be55648ec17628bcec7d4cee21358c5
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794310"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>使用通话分析来排查通话质量不良问题

本文介绍如果担任 Teams 管理员、Teams 通信支持专家或 Teams 通信支持工程师角色，如何使用呼叫分析来排查个别用户的 Microsoft Teams 通话或会议质量不佳的问题。

## <a name="call-analytics-permissions"></a>调用分析权限

本文假定你已设置呼叫分析。 如果没有，请阅读 [“为 Teams 设置呼叫分析](set-up-call-analytics.md)”。

## <a name="introduction-to-call-analytics"></a>通话分析简介

呼叫分析显示有关Office 365帐户中每个用户的 Teams 呼叫和会议的详细信息。 它包括有关设备、网络、连接和呼叫质量的信息 (其中任何一项都可能是通话或会议质量不佳) 的一个因素。 如果上传建筑物、站点和租户信息，此信息也将显示在每个呼叫和会议中。 使用呼叫分析来帮助你找出用户通话或会议体验不佳的原因。

呼叫分析显示呼叫或会议的每一站-例如，从一个参与者到另一个参与者。 通过分析这些详细信息，Teams 管理员可以隔离问题区域并确定质量不佳的根本原因。

作为 Teams 管理员，可以完全访问每个用户的所有通话分析数据。 此外，还可以分配 Azure Active Directory 角色来支持员工。 若要了解有关这些角色的详细信息，请阅读 [“授予支持人员和支持人员”的权限](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)。 请勿错过[每个 Teams 支持角色的作用？](#what-does-each-teams-support-role-do)

## <a name="where-to-find-per-user-call-analytics"></a>查找每个用户呼叫分析的位置

若要查看用户的所有呼叫信息和数据，请转到 [Teams 管理中心](https://admin.teams.microsoft.com)。 在 **“用户**”下，选择一个用户，然后在用户的个人资料页上打开“ **会议&呼叫** ”选项卡。 在这里，你将找到该用户过去 30 天的所有呼叫和会议。

![所有分析用户数据的屏幕截图。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

若要获取有关给定会话的其他信息，包括详细的媒体和网络统计信息，请单击会话以查看详细信息。

![呼叫分析用户会话数据的屏幕截图。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

## <a name="what-does-each-teams-support-role-do"></a>每个 Teams 支持角色的作用是什么？

**Teams 通信支持专家** (第 1 层支持) 处理基本的呼叫质量问题。 他们不调查会议的问题。 相反，他们收集相关信息，然后升级到 Teams 通信支持工程师。

**Teams 通信支持工程师** (第 2 层支持) 查看 Teams 通信支持专家隐藏的详细呼叫日志中的信息。 下表列出了每个 Teams 通信支持角色可用的信息。

下表介绍了每个通信支持角色的每个用户信息。

|活动|信息|什么通信<br>支持 *专家* 查看|什么通信<br>支持 *工程师* 看到|
|---|---|---|---|
|**呼叫**|调用方名称|只有代理搜索的用户的名称。|用户名。|
||收件人姓名|显示为内部用户或外部用户。|收件人姓名。|
||主叫方电话号码|除最后三位数字外，整个电话号码都混淆了星号符号。 例如，15552823\*\*\*。|除最后三位数字外，整个电话号码都混淆了星号符号。 例如，15552823\*\*\*。|
||收件人电话号码|除最后三位数字外，整个电话号码都混淆了星号符号。 例如，15552823\*\*\*。|除最后三位数字外，整个电话号码都混淆了星号符号。 例如，15552823\*\*\*。|
||**呼叫详细信息** \>**“高级**”选项卡|未显示信息。|显示的所有详细信息，例如设备名称、IP 地址、子网映射等。|
||**呼叫详细信息** \>**先进** \>**“调试”** 选项卡|未显示信息。|显示的所有详细信息，例如 DNS 后缀和 SSID。|
|**会议**|参与者姓名|只有代理搜索的用户的名称。 其他标识为内部用户或外部用户的参与者。|显示的所有名称。|
||参与者计数|参与者数。|参与者数。|
||会话详细信息|显示异常的会话详细信息。 仅显示代理搜索的用户的名称。 其他标识为内部用户或外部用户的参与者。 最后三个数字的电话号码混淆了星号符号。|显示的会话详细信息。 显示的用户名和会话详细信息。 最后三个数字的电话号码混淆了星号符号。|
||||

> [!NOTE]
> “高级”选项卡的“其他”部分和“调试”选项卡中包含的信息包含遥测数据和服务诊断数据，用于帮助 Microsoft 支持工程师。 如果没有可用于支持工程师的其他数据的上下文，它可能看起来是冗余的、不准确的或令人困惑的。 虽然我们将其提供给在排查呼叫问题方面寻找其他详细信息的高级用户，但我们不建议在没有 Microsoft 支持的情况下基于此数据做出判断。

## <a name="troubleshoot-user-call-quality-problems"></a>排查用户呼叫质量问题

1. 打开 Teams 管理中心 (<https://admin.teams.microsoft.com>) 并使用 Teams 通信支持或 Teams 管理员凭据登录。

2. 在 **仪表板** 上的 **“用户搜索**”中，开始键入要排查其呼叫的用户的名称或 SIP 地址，或选择 **“查看用户** ”以查看用户列表。

3. 从列表中选择用户。

4. 选择 **呼叫历史记录**，然后选择要进行故障排除的呼叫或会议。

5. 选择 **“高级** ”选项卡，然后查找指示通话质量差或连接问题的黄色和红色项目。

   在每个呼叫或会议的会话详细信息中，小问题以黄色显示。 如果某样东西是黄色的，它超出了正常范围，它可能是导致问题的原因，但它不太可能是问题的主要原因。 如果出现红色，则这是一个重大问题，并且可能是导致此会话通话质量不佳的主要原因。

在极少数情况下，音频会话不会收到体验质量数据。 通常，这是由删除的调用或与客户端的连接终止时导致的。 发生这种情况时，会话分级 **不可用**。

对于具有 QoE) 数据 (体验质量的音频会话，下表描述了将会话限定为 **较差** 的重大问题。

|问题|区域|说明|
|---|---|---|
|呼叫设置|会话|错误代码 Ms-diag 20-29 指示调用设置失败。 用户无法加入呼叫或会议。|
|音频网络分类通话不良|会话|遇到数据包丢失、抖动、NMOS 降级、RTT 或隐藏比率 () 等网络质量问题。|
|设备无法正常运行|Device|设备无法正常运行。 设备功能不正常比率为： <p> DeviceRenderNotFunctioningEventRatio >= 0.005 <br>  DeviceCaptureNotFunctioningEventRatio >= 0.005|
||||

## <a name="related-topics"></a>相关主题

[设置每用户呼叫分析](set-up-call-analytics.md)
