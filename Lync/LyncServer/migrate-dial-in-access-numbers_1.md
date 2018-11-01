---
title: 迁移拨入访问号码
TOCTitle: 迁移拨入访问号码
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204898(v=OCS.15)
ms:contentKeyID: 49312893
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 迁移拨入访问号码

 

_**上一次修改主题：** 2012-09-26_

迁移拨入访问号码时需要执行两个步骤：运行 **Import-CsLegacyConfiguration** cmdlet（已在 [导入策略和设置](import-policies-and-settings.md)的前面部分完成），以便迁移拨号计划和其他拨入访问号码设置，然后运行 **Move-CsApplicationEndpoint** cmdlet 以迁移联系对象。

## 迁移拨入访问号码

1.  打开 Office Communications Server 2007 R2 管理工具。

2.  在控制台树中，右键单击林节点，单击“属性”，然后单击“会议助理属性”。

3.  在“访问电话号码”选项卡上，单击“由池提供服务”，按照访问电话号码的关联池排序这些号码，然后确定要从其中迁移的池的所有访问号码。

4.  要确定每个访问号码的 SIP URI，请双击相应访问号码以打开“编辑会议助理号码”对话框，然后在“SIP URI”下进行查找。

5.  打开 Lync Server 命令行管理程序。

6.  要将每个拨入访问号码移动到 Lync Server 2013 上承载的池，请运行：
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  在 Office Communications Server 2007 R2 管理工具中，在“访问电话号码”选项卡上，确认要从中迁移的 Office Communications Server 2007 R2 池中没有保留任何拨入访问号码。

