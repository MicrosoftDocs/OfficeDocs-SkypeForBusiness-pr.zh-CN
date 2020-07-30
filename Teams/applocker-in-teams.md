---
title: AppLocker 控件策略
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解如何启用 AppLocker 应用程序控制策略的团队桌面客户端应用程序。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4e70fc4502851137494c316db9eff7faefc140d1
ms.sourcegitcommit: c573b0be535fcf927ae01d60a7eb8fbf1aec271d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2020
ms.locfileid: "46526688"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Microsoft 团队中的应用程序控制策略 AppLocker

本文介绍如何启用 AppLocker 应用程序控制策略的团队桌面客户端应用。 使用 AppLocker 旨在限制非管理用户执行的程序和脚本执行。 有关 AppLocker 的详细信息和指南，请参阅[什么是 applocker？](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)。

启用具有 AppLocker 的团队的过程需要创建基于 AppLocker 的允许列表策略。 使用组策略管理软件和/或用于 AppLocker 的 Windows PowerShell cmdlet 创建策略（有关详细信息，请参阅[AppLocker 技术参考](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)）。 AppLocker 策略以 XML 格式保存，并且可以通过任何文本或 XML 编辑器进行编辑。

## <a name="teams-allow-list-with-applocker"></a>团队允许列表包含 AppLocker

AppLocker 规则组织为规则集合。 AppLocker 规则适用于目标应用，它们是构成 AppLocker 策略的组件。  

为了允许团队，我们建议你使用[发布者条件规则](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker)，因为所有团队应用文件都经过数字签名。
  
我们不建议使用路径规则，因为团队安装目录可由用户写入。 我们也不建议使用哈希规则，因为每次更新团队客户端应用时，都必须更新规则。

由于团队桌面可执行文件经过数字签名，发布者条件基于其数字签名和嵌入的版本属性来标识应用文件。 数字签名包含有关创建应用文件（发布者）的公司的信息。 从二进制资源获取的版本信息，包括文件所属的产品的名称以及应用程序文件的版本号。

### <a name="example-of-publisher-condition-rules"></a>Publisher 条件规则的示例

对于团队客户端应用（所有文件，所有版本），请将以下内容添加到可执行规则 & DLL 规则：

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>相关主题
[什么是 AppLocker？](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
[AppLocker 技术参考](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)
