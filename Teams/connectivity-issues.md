---
title: 排查 Teams 客户端的连接问题
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: 8974aa7cf54ab61cb15650b839185daad1b82cc7
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562161"
---
# <a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a>使用 Microsoft Teams 客户端解决连接性问题

已发现的有关 Microsoft Teams 客户端的大多数问题都可追溯到防火墙或代理连接。 验证是否在防火墙或代理中打开了所需的 URL、IP 地址和端口可最大程度地减少不必要的故障排除。 有关 Microsoft Teams 所需的 URL 和 IP 的特定信息，请参阅 [Microsoft 365 和Office 365 URL 和 IP 地址](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)支持文章。 以下方案需要在防火墙中打开特定 URL 和端口。

- 身份验证

- Microsoft Teams 客户端连接

- 协作

- 媒体

- 共享服务

- 第三方集成

- Skype for Business 互操作性

- Skype for Business 客户端互操作性

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a>当 Teams 处于脱机状态或带宽不足时

好消息是，即使你处于脱机状态或在低带宽条件下运行，Teams 也将继续运行。 Teams 将现有聊天的所有未发送邮件保存 (长达 24 小时) 并在你重新联机后立即发送。 如果脱机时间超过 24 小时，Teams 允许你选择重新发送或删除未发送的消息。 我们正在努力将此功能添加到新聊天，并在可用时更新此文档。

## <a name="related-topics"></a>相关主题

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)