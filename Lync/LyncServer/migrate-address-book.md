---
title: 迁移通讯簿
TOCTitle: 迁移通讯簿
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205160(v=OCS.15)
ms:contentKeyID: 49313902
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 迁移通讯簿

 

_**上一次修改主题：** 2012-10-09_

一般来说， Lync Server 2010 通讯簿随拓扑的其余部分一起迁移。但是，如果在 Lync Server 2010 环境中自定义了以下项，可能需要执行一些迁移后步骤：

  - 将 **PartitionbyOU** WMI 属性设置为按组织单位 (OU) 对通讯簿条目进行分组。

  - 自定义了通讯簿规范化规则。

  - 已将 **UseNormalizationRules** 参数的默认值更改为 False。

**分组的通讯簿条目**

如果将 **PartitionbyOU** WMI 属性设置为 True 以针对每个 OU 创建通讯簿，并且您希望继续对通讯簿条目分组，则需要设置用户和联系人的 **msRTCSIP-GroupingId** Active Directory 属性。您可能希望对通讯簿条目分组以限制通讯簿的搜索范围。要使用 **msRTCSIP-GroupingId** 属性，请编写用于填充该属性的脚本，向您希望组合在一起的所有用户分配相同的值。例如，向一个 OU 中的所有用户分配一个值。

**通讯簿规范化规则**

如果在 Lync Server 2010 环境中自定义了通讯簿规范化规则，则必须将自定义的规则迁移到试点池。如果未自定义通讯簿规范化规则，则通讯簿服务没有要迁移的内容。 Lync Server 2013 的默认规范化规则与 Lync Server 2010 的默认规则相同。请按照本节后面的过程来迁移自定义规范化规则。

> [!NOTE]  
> 如果您的组织使用远程呼叫控制并且您自定义了通讯簿规范化规则，则必须首先执行本主题中的过程，然后才能使用远程呼叫控制。要执行该过程，需要具有 RTCUniversalServerAdmins 组成员的身份或同等权限。


**UseNormalizationRules 设置为 False**

如果将 **UseNormalizationRules** 的值设置为 False，以便用户可以使用在 Active Directory 域服务 中定义的电话号码，而无需使 Lync Server 2013 应用规范化规则，则需要将 **UseNormalizationRules** 和 **IgnoreGenericRules** 参数设置为 True。请按照本节后面的过程将这些参数设置为 True。

## 迁移通讯簿自定义规范化规则

1.  在通讯簿共享文件夹的根目录下查找 Company\_Phone\_Number\_Normalization\_Rules.txt 文件，并将它复制到 Lync Server 2013 试点池中通讯簿共享文件夹的根目录下。
    
    > [!NOTE]
    > 示例“通讯簿服务”规范化规则已安装在您的 ABS Web 组件文件目录中。路径为 <strong>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt</strong>。可以将此文件复制到通讯簿共享文件夹的根目录，并将其重命名为 <strong>Company_Phone_Number_Normalization_Rules.txt</strong>。例如， <strong>$serverX</strong> 中共享的通讯簿，路径将类似于：<strong>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</strong>。


2.  使用文本编辑器（如“记事本”）打开 Company\_Phone\_Number\_Normalization\_Rules.txt 文件。

3.  某些类型的条目在 Lync Server 2013 中无法正常工作。请在文件中查找该步骤中所述的这些条目类型，根据需要编辑它们，并将更改保存到试点池中的通讯簿共享文件夹。
    
    包含必要空格或标点的字符串会导致规范化规则失败，因为系统会将这些字符从输入到规范化规则的字符串中删除。如果您有包含必要空格或标点的字符串，则需要修改这些字符串。例如，以下字符串将导致规范化规则失败：
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    以下字符串不会导致规范化规则失败：
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

## 将 UseNormalizationRules 和 IgnoreGenericRules 设置为 true

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  执行下列操作之一：
    
      - 如果您的部署仅包括 Lync Server 2013，请在全局级别运行以下 cmdlet，以将 **UseNormalizationRules** 和 **IgnoreGenericRules** 的值更改为 True：
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - 如果您的部署包括 Lync Server 2013 和 Lync Server 2010 或 Office Communications Server 2007 R2 的组合，则运行以下 cmdlet 并将其分配给拓扑中的每个 Lync Server 2013 池：
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  等待在所有池上进行 中央管理存储 复制。

4.  修改针对您的部署的电话规范化规则文件“Company\_Phone\_Number\_Normalization\_Rules.txt”，以清除内容。该文件位于每个 Lync Server 2013 池的文件共享上。如果该文件不存在，请创建名为“Company\_Phone\_Number\_Normalization\_Rules.txt”的空文件。

5.  等待几分钟，以便所有 前端池读取新文件。

6.  在您的部署中的每个 Lync Server 2013 池上运行以下 cmdlet：
    
        Update-CsAddressBook

