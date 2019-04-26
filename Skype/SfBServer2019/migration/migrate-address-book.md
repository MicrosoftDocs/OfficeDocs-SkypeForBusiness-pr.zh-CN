---
title: 迁移通讯簿
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 一般情况下，您的拓扑的其余部分以及迁移通讯簿。 但是，您可能需要执行一些迁移后的步骤，如果旧环境中自定义以下：
ms.openlocfilehash: 728ae97270cd8451178c6ef962f05e0351118119
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238422"
---
# <a name="migrate-address-book"></a>迁移通讯簿

一般情况下，您的拓扑的其余部分以及迁移通讯簿。 但是，您可能需要执行一些迁移后的步骤，如果旧环境中自定义以下： 

- 自定义通讯簿规范化规则。

- 更改将**UseNormalizationRules**参数的默认值为 False。 


 **通讯簿规范化规则**

如果旧环境中自定义通讯簿规范化规则，您必须将自定义的规则迁移到试点池。 如果您未自定义通讯簿规范化规则，则必须 nothing 通讯簿服务的迁移。 有关业务服务器 2019年的 Skype 的默认规范化规则是旧安装的默认规则相同。 按照本节迁移自定义的规范化规则后面的过程。

> [!NOTE]
> 如果您的组织使用远程呼叫控制并且您自定义通讯簿规范化规则，您必须在本主题中执行过程，然后才能使用远程呼叫控制。 过程要求中的 RTCUniversalServerAdmins 组或同等权限的成员身份。 

 **UseNormalizationRules 设置为 False**

如果您将值设置为**UseNormalizationRules**为 False，以便用户可以使用电话号码，如中定义无业务服务器 2019 Skype 的 Active Directory 域服务应用规范化规则，您需要设置**UseNormalizationRules**和**IgnoreGenericRules**参数为 True。 按照此部分将这些参数设置为 True 中稍后介绍的过程。 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>迁移通讯簿自定义规范化规则

1. 通讯簿共享文件夹的根目录中查找 Company_Phone_Number_Normalization_Rules.txt 文件，并将其复制到您的业务服务器 2019年试点池的 Skype 中的通讯簿共享文件夹的根目录。

    > [!NOTE]
    > 已在 ABS Web 组件文件目录中安装通讯簿规范化规则示例。 路径为 **$installedDriveLetter: \Program Files\Microsoft Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt 的 Skype**。 可复制此文件，并将其重命名为**Company_Phone_Number_Normalization_Rules.txt**为通讯簿共享的文件夹的根目录。 例如，通讯簿中 **$serverX**共享，则路径将会类似于： ** \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**。 

2. 使用文本编辑器，如记事本中，打开 Company_Phone_Number_Normalization_Rules.txt 文件。

3. 某些类型的项将无法正常工作 Skype 中的业务服务器 2019年。 在此步骤中所述的条目的类型的文件中查找、 根据需要，对其进行编辑和保存对试点池中通讯簿共享文件夹的更改。

    包含需要的空格或标点符号原因规范化规则失败，因为这些字符去除超出输入到的规范化规则的字符串的字符串。 如果必须包含必需的空格或标点的字符串，您需要修改字符串。 例如，以下字符串会导致规范化规则失败：

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    以下字符串不会导致规范化规则失败：

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>若要将 UseNormalizationRules 和 IgnoreGenericRules 设置为 true

1. 为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**，都单击**Microsoft Skype 的业务服务器 2019年**，，然后都单击**Skype 的业务 Server Management Shell**。

2. 请执行下列操作之一：

   - 如果您的部署包括仅 Skype 的业务服务器 2019，在要以**将 UseNormalizationRules**和**IgnoreGenericRules**的值更改为 True 的全局级别运行以下 cmdlet: 

   ```
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - 如果您的部署包括业务服务器 2019年和旧安装 Skype 的组合，运行以下 cmdlet 并将其分配给每个 Skype 业务服务器 2019年池拓扑中：

   ```
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. 等待在所有池上发生中央管理存储复制。

4. 修改电话规范化规则文件，若要清除的内容部署"Company_Phone_Number_Normalization_Rules.txt"。 文件是在每个 Skype 业务服务器 2019年池的文件共享上。 如果文件不存在，然后创建一个名为"Company_Phone_Number_Normalization_Rules.txt"的空文件。

5. 等待几分钟，以便所有前端池读取新文件。

6. 在部署中的业务服务器 2019年池的每个 Skype 上运行以下 cmdlet:

   ```
   Update-CsAddressBook
   ```


