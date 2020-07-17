---
title: 迁移通讯簿
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 通常情况下，通讯簿与拓扑的其余部分一起迁移。 但是，如果您在旧版环境中自定义以下迁移步骤，则可能需要执行某些迁移后步骤：
ms.openlocfilehash: 6d2ccf0d38814d149495518a71f888f0c2999d24
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752834"
---
# <a name="migrate-address-book"></a>迁移通讯簿

通常情况下，通讯簿与拓扑的其余部分一起迁移。 但是，如果您在旧版环境中自定义以下迁移步骤，则可能需要执行某些迁移后步骤： 

- 自定义了通讯簿规范化规则。

- 将**UseNormalizationRules**参数的默认值更改为 False。 


 **通讯簿规范化规则**

如果您在旧版环境中自定义了通讯簿规范化规则，则必须将自定义规则迁移到您的引导池。 如果未自定义通讯簿规范化规则，则通讯簿服务没有要迁移的内容。 Skype for business Server 2019 的默认规范化规则与旧安装的默认规则相同。 按照本节后面的过程操作，迁移自定义的规范化规则。

> [!NOTE]
> 如果您的组织使用远程呼叫控制并且您自定义了通讯簿规范化规则，则必须首先执行本主题中的过程，然后才能使用远程呼叫控制。要执行该过程，需要具有 RTCUniversalServerAdmins 组成员的身份或同等权限。 

 **UseNormalizationRules 设置为 False**

如果将**UseNormalizationRules**的值设置为 False，以便用户可以使用在 Active Directory 域服务中定义的电话号码，而无需使用 Skype For business Server 2019 应用规范化规则，则需要将**UseNormalizationRules**和**IgnoreGenericRules**参数设置为 True。 按照本节后面的过程操作，将这些参数设置为 True。 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>迁移通讯簿自定义规范化规则

1. 在通讯簿共享文件夹的根目录中查找 Company_Phone_Number_Normalization_Rules.txt 文件，并将其复制到 Skype for Business Server 2019 试行版池中的通讯簿共享文件夹的根目录中。

    > [!NOTE]
    > 示例“通讯簿服务”规范化规则已安装在您的 ABS Web 组件文件目录中。 路径为 **$installedDriveLetter： \Program Files\Microsoft Skype for Business Server 2019 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**。 可以将此文件作为**Company_Phone_Number_Normalization_Rules.txt**复制和重命名为通讯簿共享文件夹的根目录。 例如， **$serverX**中共享的通讯簿，该路径将类似于： ** \\ $serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**。 

2. 使用文本编辑器（如“记事本”）打开 Company_Phone_Number_Normalization_Rules.txt 文件。

3. 在 Skype for business Server 2019 中，某些类型的条目将无法正常工作。 请在文件中查找该步骤中所述的这些条目类型，根据需要编辑它们，并将更改保存到试点池中的通讯簿共享文件夹。

    包含必要空格或标点的字符串会导致规范化规则失败，因为系统会将这些字符从输入到规范化规则的字符串中删除。如果您有包含必要空格或标点的字符串，则需要修改这些字符串。例如，以下字符串将导致规范化规则失败：

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    以下字符串不会导致规范化规则失败：

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>将 UseNormalizationRules 和 IgnoreGenericRules 设置为 true

1. 启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Skype for business server 2019**"，然后单击 " **Skype for business server Management Shell**"。

2. 执行下列操作之一：

   - 如果您的部署仅包括 Skype for Business Server 2019，请在全局级别运行以下 cmdlet，以将**UseNormalizationRules**和**IgnoreGenericRules**的值更改为 True： 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - 如果您的部署包含 Skype for business Server 2019 和旧安装的组合，请运行以下 cmdlet，并将其分配给拓扑中的每个 Skype for Business Server 2019 池：

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. 等待中央管理存储复制在所有池上进行。

4. 修改电话规范化规则文件 "Company_Phone_Number_Normalization_Rules.txt"，以供您的部署清除内容。 文件位于每个 Skype for Business Server 2019 池的文件共享中。 如果文件不存在，则创建一个名为 "Company_Phone_Number_Normalization_Rules.txt" 的空文件。

5. 等待几分钟，让所有前端池都能读取新文件。

6. 在部署中的每个 Skype for Business Server 2019 池中运行以下 cmdlet：

   ```PowerShell
   Update-CsAddressBook
   ```


