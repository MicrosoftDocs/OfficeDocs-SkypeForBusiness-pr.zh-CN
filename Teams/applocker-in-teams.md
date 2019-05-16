---
title: AppLocker 应用程序控制策略中的 Microsoft 团队
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
description: 了解如何启用 AppLocker 应用程序控制策略的团队桌面客户端应用程序。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04379cad0ab224915a02475b010f908d486284cc
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34063204"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>AppLocker 应用程序控制策略中的 Microsoft 团队

本文介绍如何启用团队桌面客户端应用程序与 AppLocker 应用程序控制策略。 利用 AppLocker 旨在通过非管理员用户限制程序和脚本执行。 有关详细信息和 AppLocker 指南，请参阅[AppLocker 是什么？](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)。

启用与 AppLocker 团队的过程需要创建的基于 AppLocker 添加到白名单策略。 使用组策略管理软件和/或 AppLocker 使用 Windows PowerShell cmdlet 创建策略 （请参阅[AppLocker 技术参考](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)（英文） 的详细信息）。 AppLocker 策略以 XML 格式保存，并且可以使用任何文本编辑器或 XML 编辑器进行编辑。

## <a name="teams-whitelisting-with-applocker"></a>与 AppLocker 团队白

AppLocker 规则均分成各种规则的集合。 AppLocker 规则适用于目标应用程序，它们是组成 AppLocker 策略的组件。  

向白名单工作组，我们建议您使用[publisher 条件规则](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker)，因为所有团队应用程序文件经过数字都签名。
  
我们不建议使用路径规则，因为团队安装目录是用户可写。 由于这些规则将具有要更新每次更新团队客户端应用程序，我们还不建议使用哈希规则。

由于团队桌面可执行文件经过数字签名，publisher 条件标识基于它的数字签名和嵌入的版本属性的应用程序文件。 数字签名包含有关创建应用程序文件 （发行商） 的公司的信息。 版本信息，可获取从二进制资源，包括该文件的一部分的产品和应用程序文件的版本号的名称。

### <a name="example-of-publisher-condition-rules"></a>Publisher 条件规则的示例

团队 （所有文件，所有版本） 的客户端将应用程序：

```
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
```

## <a name="related-topics"></a>相关主题
[什么是 AppLocker？](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
 [AppLocker 技术参考](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)