---
title: 来电显示
TOCTitle: 来电显示
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49888620
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 来电显示

 

_**上一次修改主题：** 2016-12-08_

使用 Lync Server 2010，可将被呼叫者的电话号码（即呼叫的电话号码）从 E.164 格式转换为*中继对等方*（即关联的网关、专用交换机 (PBX) 或 SIP 中继）需要的本地拨号格式。为此，必须定义一个或多个转换规则，以便在将请求 URI 路由至中继对等方之前对其执行转换。

> [!IMPORTANT]  
> 将一个或多个转换规则与企业语音中继配置进行关联的功能可用作在中继对等方上配置转换规则的<em>备选方法</em>。如果已在中继对等方上配置转换规则，则不要将任何转换规则与企业语音中继配置相关联，因为这两个规则可能会发生冲突。


可以使用以下任一方法创建或修改转换规则：

  - 使用“构建转换规则”工具指定起始数字、长度、要删除的数字和添加的数字的值，然后使 Lync Server 控制面板 生成对应的匹配模式和转换规则。

  - 手动编写正则表达式以定义匹配模式和转换规则。

> [!NOTE]  
> 有关如何编写正则表达式的信息，请参阅“.NET Framework 正则表达式”，网址为 <a href="http://go.microsoft.com/fwlink/?linkid=140927%26clcid=0x804" class="uri">http://go.microsoft.com/fwlink/?linkid=140927&amp;clcid=0x804</a>。



## 本部分内容

  - [使用“建立转换规则”工具创建或修改转换规则](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [手动创建或修改转换规则](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

## 另请参阅

#### 概念

[Lync Server 2013 中的来电显示](lync-server-2013-caller-id-presentation.md)

