---
title: AppLocker 控制策略
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
description: 了解如何使用 AppLocker 应用程序控制策略启用 Teams 桌面客户端应用程序。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d6e6040956ba5e5469076b4fbbab337f58268c68
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120844"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Microsoft Teams 中的 AppLocker 应用程序控制策略

本文介绍如何使用 AppLocker 应用程序控制策略启用 Teams 桌面客户端应用。 AppLocker 的使用旨在限制非管理用户的程序和脚本执行。 有关 AppLocker 的信息和指南，请参阅[什么是 AppLocker？。](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)

使用 AppLocker 启用 Teams 的过程需要创建基于 AppLocker 的允许列表策略。 策略是使用组策略管理软件和/或使用 Windows PowerShell cmdlet for AppLocker 创建的 (请参阅 [AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) 技术参考，) 。 AppLocker 策略以 XML 格式保存，可以使用任何文本或 XML 编辑器进行编辑。

## <a name="teams-allow-list-with-applocker"></a>具有 AppLocker 的团队允许列表

AppLocker 规则组织成规则集合。 AppLocker 规则适用于目标应用，它们是构成 AppLocker 策略的组件。  

若要允许 Teams，建议使用发布者条件 [规则](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) ，因为所有 Teams 应用文件都是数字签名的。
  
不建议使用路径规则，因为 Teams 安装目录是用户可写的。 我们不建议使用哈希规则，因为每次更新 Teams 客户端应用时，必须更新规则。

由于 Teams 桌面可执行文件已进行数字签名，因此发布者条件会基于应用的数字签名和嵌入式版本属性来标识应用文件。 数字签名包含有关创建应用文件的公司的信息， (发布者) 。 从二进制资源获取的版本信息包括该文件所包含产品的名称和应用程序文件的版本号。

### <a name="example-of-publisher-condition-rules"></a>发布者条件规则示例

对于包含所有 (Teams 客户端应用，所有) 将以下内容添加到 DLL 规则的可执行&规则：

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>相关主题
[什么是 AppLocker？](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
[AppLocker 技术参考](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)