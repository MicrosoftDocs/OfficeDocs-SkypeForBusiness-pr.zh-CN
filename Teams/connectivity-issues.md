---
title: 排查客户端Teams问题
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: 解决 Microsoft Teams 客户端的连接问题（主要由防火墙或代理连接导致），并了解如何进行修复。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 25a4fc51e0bb8dec810ce921e3678a529ee7a4cf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101158"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a>使用 Microsoft Teams 客户端解决连接性问题
==============================================================

已发现的有关 Microsoft Teams 客户端的大多数问题都可追溯到防火墙或代理连接。 验证是否在防火墙或代理中打开了所需的 URL、IP 地址和端口可最大程度地减少不必要的故障排除。 有关应用程序所需的 URL 和 IP Microsoft Teams，请参阅 Microsoft 365 和 Office 365 URL 和[IP 地址](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)支持一文。 以下方案需要在防火墙中打开特定 URL 和端口。

- 身份验证

- Microsoft Teams 客户端连接

- 协作

- 媒体

- 共享服务

- 第三方集成

- Skype for Business 互操作性

- Skype for Business 客户端互操作性

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a>当Teams处于脱机或低带宽情况下时

好消息是，Teams处于脱机状态或低带宽情况下仍保持运行。 Teams将现有聊天的所有未发送消息 (保存最多 24 小时) 当您重新联机时立即发送这些消息。 如果脱机时间超过 24 小时，Teams选择重新发送或删除未发送的邮件。 我们正在努力将此功能添加到新聊天，并且将在本文档可用时更新此文档。

## <a name="related-topics"></a>相关主题

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)