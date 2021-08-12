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
description: 了解如何使用 AppLocker Teams策略启用桌面客户端应用程序。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b68d698ffcb703e70e12f3801ff70fb0719bb17cb09e23facf47121529a86b0b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288440"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>应用中的 AppLocker 应用程序控制Microsoft Teams

本文介绍如何使用 AppLocker Teams策略启用桌面客户端应用。 AppLocker 的使用旨在限制非管理用户的程序和脚本执行。 有关 AppLocker 的信息和指南，请参阅[什么是 AppLocker？。](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)

使用 AppLocker Teams应用的过程需要创建基于 AppLocker 的允许列表策略。 策略是使用组策略管理软件和/或使用 Windows PowerShell cmdlet 为 AppLocker 创建的 (请参阅[AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)技术参考，了解) 。 AppLocker 策略以 XML 格式保存，可以使用任何文本或 XML 编辑器进行编辑。

## <a name="teams-allow-list-with-applocker"></a>Teams AppLocker 创建允许列表

AppLocker 规则组织成规则集合。 AppLocker 规则适用于目标应用，它们是构成 AppLocker 策略的组件。  

若要Teams，建议使用发布者条件规则，因为Teams文件都是数字签名[](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker)的。
  
不建议使用路径规则，因为Teams目录是用户可写的。 我们不建议使用哈希规则，因为每次更新客户端应用时，Teams更新规则。

由于Teams可执行文件是数字签名的，因此发布者条件会基于应用的数字签名和嵌入式版本属性来标识应用文件。 数字签名包含有关创建应用文件的公司的信息， (发布者) 。 从二进制资源获取的版本信息包括该文件所包含产品的名称和应用程序文件的版本号。

### <a name="example-of-publisher-condition-rules"></a>发布者条件规则示例

对于Teams客户端应用 (文件，所有版本) 添加到 DLL 规则的可执行&规则：

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>相关主题
[什么是 AppLocker？](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
[AppLocker 技术参考](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)