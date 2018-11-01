---
title: （建议）创建会议目录
TOCTitle: （建议）创建会议目录
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63232643
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# （建议）创建会议目录

 

_**上一次修改主题：** 2014-10-03_

会议目录将维护使用 Lync 2013 时参与者加入会议所使用的会议 ID（包含字母数字）与电话拨入式会议参与者加入会议所使用的会议 ID（仅包含数字）之间的映射。会议 ID 的格式如下：

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

创建多个会议目录可以确保会议 ID 短暂停留，直到创建了大量会议。如果组织中每个用户的会议数量为典型值，建议为池中的每 999 个用户创建一个会议目录。通过使用此指南，通常可使会议 ID 保持较小数量。但是，只要会议目录数（所有池中）超过 9，会议 ID 长度就会增加以支持更多会议。

## 创建会议目录

1.  在 Lync Server 命令行管理程序 中，键入以下 cmdlet：
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    例如，使用以下命令可创建一个标识为 42 的会议目录，该会议目录在池 atl-cs-001.litwareinc.com 中托管：
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

## 另请参阅

#### 概念

[电话拨入式会议要求](lync-server-2013-dial-in-conferencing-requirements.md)  

#### 其他资源

[New-CsConferenceDirectory](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsConferenceDirectory)

