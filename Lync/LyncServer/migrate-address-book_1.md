---
title: 迁移通讯簿
TOCTitle: 迁移通讯簿
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205198(v=OCS.15)
ms:contentKeyID: 49314022
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 迁移通讯簿

 

_**上一次修改主题：** 2012-10-02_

**迁移通讯簿自定义规范化规则**

1.  在通讯簿共享文件夹的根目录下查找 Company\_Phone\_Number\_Normalization\_Rules.txt 文件，并将它复制到 Lync Server 2013 试点池中通讯簿共享文件夹的根目录下。
    
    > [!NOTE]
    > 示例“通讯簿服务”规范化规则已安装在您的 ABS Web 组件文件目录中。路径为 <strong>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt</strong>。可以将此文件复制到通讯簿共享文件夹的根目录，并将其重命名为 <strong>Company_Phone_Number_Normalization_Rules.txt</strong>。例如，<strong>$serverX</strong> 中共享的通讯簿，路径将类似于：<strong>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</strong>。


2.  使用文本编辑器（如“记事本”）打开 Company\_Phone\_Number\_Normalization\_Rules.txt 文件。

3.  某些类型的条目在 Lync Server 2013 中无法正常工作。请在文件中查找该步骤中所述的这些条目类型，根据需要编辑它们，并将更改保存到试点池中的通讯簿共享文件夹。
    
    包含必要空格或标点的字符串会导致规范化规则失败，因为系统会将这些字符从输入到规范化规则的字符串中删除。如果您有包含必要空格或标点的字符串，则需要修改这些字符串。例如，以下字符串将导致规范化规则失败：
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    以下字符串不会导致规范化规则失败：
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

