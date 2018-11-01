---
title: 配置辅助位置信息服务
TOCTitle: 配置辅助位置信息服务
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398138(v=OCS.15)
ms:contentKeyID: 49311916
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置辅助位置信息服务

 

_**上一次修改主题：** 2012-10-30_

Lync Server 2013 提供了一个 Web 服务接口，可用于将位置信息服务指向辅助位置源 (SLS) 数据库。连接到 SLS 数据库的 Web 服务接口必须符合位置信息服务 WSDL。如果位置数据库和辅助位置数据库均已配置，则位置信息服务将首先查询位置数据库，如果没有找到匹配项，则将位置请求从客户端发送到 SLS 数据库。如果位置存在于 SLS 中，则位置信息服务会将位置发送回客户端。

有关详细信息，请参阅 Lync Server 命令行管理程序文档中有关以下 cmdlet 的内容：

  - **Set-CsWebServiceConfiguration**

## 配置辅助位置数据库

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  运行以下 cmdlet 为辅助位置数据库位置配置 URL。
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>"

