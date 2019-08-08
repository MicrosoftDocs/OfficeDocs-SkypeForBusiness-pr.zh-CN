---
title: 迁移通讯簿
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '通常, 通讯簿与拓扑的其余部分一起迁移。 但是, 如果你在旧环境中自定义以下迁移步骤, 你可能需要执行一些迁移后步骤:'
ms.openlocfilehash: 4a3a85715b73c3a6b5996ba677b0647c87a8db1e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238051"
---
# <a name="migrate-address-book"></a>迁移通讯簿

通常, 通讯簿与拓扑的其余部分一起迁移。 但是, 如果你在旧环境中自定义以下迁移步骤, 你可能需要执行一些迁移后步骤: 

- 自定义通讯簿规范化规则。

- 将**UseNormalizationRules**参数的默认值更改为 False。 


 **通讯簿规范化规则**

如果你在旧环境中自定义了通讯簿规范化规则, 则必须将自定义规则迁移到你的试点池。 如果您没有自定义通讯簿规范化规则, 则不能为通讯簿服务迁移任何内容。 Skype for business Server 2019 的默认规范化规则与旧安装的默认规则相同。 按照本部分后面的过程迁移自定义的规范化规则。

> [!NOTE]
> 如果您的组织使用远程呼叫控制, 并且您自定义了通讯簿规范化规则, 则必须先执行本主题中的过程, 然后才能使用远程呼叫控制。 该过程需要 RTCUniversalServerAdmins 组或等效权限中的成员身份。 

 **UseNormalizationRules 设置为 False**

如果你将**UseNormalizationRules**的值设置为 False, 以便用户可以使用在 Active Directory 域服务中定义的电话号码, 而无需使用 Skype For business Server 2019 应用规范化规则, 你需要将**UseNormalizationRules**和**IgnoreGenericRules**参数设置为 True。 按照本部分后面的过程将这些参数设置为 True。 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>迁移通讯簿自定义规范化规则

1. 在 "通讯簿" 共享文件夹的根中查找 Company_Phone_Number_Normalization_Rules 文件, 并将其复制到 Skype for Business Server 2019 试验池中的 "通讯簿" 共享文件夹的根。

    > [!NOTE]
    > 示例通讯簿规范化规则已安装在你的 ABS Web 组件文件目录中。 路径为 **$installedDriveLetter: \Program Files\Microsoft Skype for Business Server 2019 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules**。 可以将此文件作为**Company_Phone_Number_Normalization_Rules**复制和重命名为通讯簿共享文件夹的根目录。 例如, **$serverX**中共享的通讯簿, 路径将类似于: ** \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**。 

2. 使用文本编辑器 (如记事本) 打开 Company_Phone_Number_Normalization_Rules 文件。

3. 在 Skype for Business Server 2019 中, 某些类型的条目将无法正常工作。 查看该文件以了解本步骤中所述的条目类型, 根据需要对其进行编辑, 并将更改保存到你的试点池中的 "通讯簿" 共享文件夹中。

    包含所需的空格或标点的字符串将导致规范化规则失败, 因为这些字符将从输入到规范化规则的字符串中去除。 如果你有包含必需的空格或标点的字符串, 则需要修改这些字符串。 例如, 以下字符串将导致规范化规则失败:

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    以下字符串不会导致规范化规则失败:

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>将 UseNormalizationRules 和 IgnoreGenericRules 设置为 true

1. 启动 Skype for Business Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft skype for business server 2019**", 然后单击 " **skype for business 服务器管理外壳**"。

2. 请执行下列操作之一：

   - 如果你的部署仅包括 Skype for Business Server 2019, 请在全局级别上运行以下 cmdlet, 将**UseNormalizationRules**和**IgnoreGenericRules**的值更改为 True: 

   ```
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - 如果你的部署包括 Skype for Business Server 2019 和旧式安装的组合, 请运行以下 cmdlet, 并将其分配给拓扑中的每个 Skype for Business Server 2019 池:

   ```
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. 等待中央管理存储复制在所有池上发生。

4. 为你的部署修改电话规范化规则文件 "Company_Phone_Number_Normalization_Rules" 以清除内容。 该文件位于每个 Skype for Business Server 2019 池的文件共享中。 如果文件不存在, 则创建一个名为 "Company_Phone_Number_Normalization_Rules" 的空文件。

5. 请等待几分钟, 让所有前端池读取新文件。

6. 在部署中的每个 Skype for Business Server 2019 池中运行以下 cmdlet:

   ```
   Update-CsAddressBook
   ```


