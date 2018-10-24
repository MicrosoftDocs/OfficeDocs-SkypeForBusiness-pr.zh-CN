---
title: Lync Server 2013：验证架构复制
TOCTitle: 验证架构复制
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412822(v=OCS.15)
ms:contentKeyID: 49313906
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中验证 Active Directory 架构复制

 

_**上一次修改主题：** 2012-10-29_

在运行林准备之前，请手动验证是否已复制架构分区。

## 手动验证架构复制

1.  以 Enterprise Admins 组成员的身份登录到域控制器。

2.  依次单击“开始”、“管理工具”、“ADSI Edit”以打开 ADSI Edit。
    
    > [!TIP]
    > 此外，还可以从命令行运行 <strong>adsiedit.msc</strong> 。


3.  在 Microsoft 管理控制台 (MMC) 树中，单击“ADSI Edit”（如果尚未选中）。

4.  在“操作”菜单上，单击“连接到”。

5.  在“连接设置”对话框中的“选择一个已知命名上下文”下，选择“架构”，然后单击“确定”。

6.  在架构容器下，搜索“CN=ms-RTC-SIP-SchemaVersion”。如果此对象存在，并且 **rangeUpper** 属性的值为 1150， **rangeLower** 属性的值为 3，则说明架构更新和复制成功。如果此对象不存在，或 **rangeUpper** 和 **rangeLower** 属性的值不是指定的值，则说明架构未经过修改或尚未复制。

## 另请参阅

#### 任务

[在 Lync Server 2013 中运行 Active Directory 架构准备](lync-server-2013-running-schema-preparation.md)  

#### 概念

[在 Lync Server 2013 中准备 Active Directory 架构](lync-server-2013-preparing-the-active-directory-schema.md)

