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
ms.localizationpriority: medium
description: 通常，通讯簿会随拓扑的其余部分一起迁移。 但是，如果您在旧环境中自定义了以下内容，您可能需要执行一些迁移后步骤：
ms.openlocfilehash: 0ef965ef67393604e257049681a64ffb3c5b8fb1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599717"
---
# <a name="migrate-address-book"></a>迁移通讯簿

通常，通讯簿会随拓扑的其余部分一起迁移。 但是，如果您在旧环境中自定义了以下内容，您可能需要执行一些迁移后步骤： 

- 自定义了通讯簿规范化规则。

- 将 **UseNormalizationRules** 参数的默认值更改为 False。 


 **通讯簿规范化规则**

如果在旧环境中自定义了通讯簿规范化规则，则必须将自定义的规则迁移到试点池。 如果未自定义通讯簿规范化规则，则通讯簿服务没有要迁移的内容。 2019 年 Skype for Business Server的默认规范化规则与旧版安装的默认规则相同。 按照本节稍后介绍的过程迁移自定义规范化规则。

> [!NOTE]
> 如果您的组织使用远程呼叫控制并且您自定义了通讯簿规范化规则，则必须首先执行本主题中的过程，然后才能使用远程呼叫控制。要执行该过程，需要具有 RTCUniversalServerAdmins 组成员的身份或同等权限。 

 **UseNormalizationRules 设置为 False**

如果将 **UseNormalizationRules** 的值设置为 False，以便用户可以使用 Active Directory 域服务中定义的电话号码，而无需 Skype for Business Server 2019 应用规范化规则，则需要将 **UseNormalizationRules** 和 **IgnoreGenericRules** 参数设置为 True。 按照本节稍后的过程操作，将这些参数设置为 True。 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>迁移通讯簿自定义规范化规则

1. 在 Company_Phone_Number_Normalization_Rules.txt 共享文件夹的根目录下查找通讯簿文件，并复制到 Skype for Business Server 2019 试点池中通讯簿共享文件夹的根目录。

    > [!NOTE]
    > 示例“通讯簿服务”规范化规则已安装在您的 ABS Web 组件文件目录中。 路径为 **$installedDriveLetter：\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**。 可以将此文件复制并重命名为Company_Phone_Number_Normalization_Rules.txt通讯簿共享文件夹的根目录。 例如，在 $serverX **中共享的** 通讯簿的路径将类似于： **\\ $serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**。 

2. 使用文本编辑器（如“记事本”）打开 Company_Phone_Number_Normalization_Rules.txt 文件。

3. 某些类型的条目在 2019 年 2 月Skype for Business Server正常运行。 请在文件中查找该步骤中所述的这些条目类型，根据需要编辑它们，并将更改保存到试点池中的通讯簿共享文件夹。

    包含必要空格或标点的字符串会导致规范化规则失败，因为系统会将这些字符从输入到规范化规则的字符串中删除。如果您有包含必要空格或标点的字符串，则需要修改这些字符串。例如，以下字符串将导致规范化规则失败：

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    以下字符串不会导致规范化规则失败：

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>将 UseNormalizationRules 和 IgnoreGenericRules 设置为 true

1. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Microsoft Skype for Business Server 2019"，** 然后单击"Skype for Business Server **命令行管理程序"。**

2. 执行下列操作之一：

   - 如果您的部署仅包括 Skype for Business Server 2019，请运行全局级别的以下 cmdlet，将 **UseNormalizationRules** 和 **IgnoreGenericRules** 的值更改为 True： 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - 如果您的部署包括 Skype for Business Server 2019 和旧安装的组合，请运行以下 cmdlet 并将其分配给拓扑中的每个 Skype for Business Server 2019 池：

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. 等待中央管理存储复制在所有池上发生。

4. 修改电话规范化规则文件"Company_Phone_Number_Normalization_Rules.txt"，以让部署清除内容。 该文件位于每个 2019 池Skype for Business Server文件共享中。 如果该文件不存在，则创建一个名为"Company_Phone_Number_Normalization_Rules.txt"的空文件。

5. 请等待几分钟，所有前端池读取新文件。

6. 在部署中的每个 Skype for Business Server 2019 池运行以下 cmdlet：

   ```PowerShell
   Update-CsAddressBook
   ```


