---
title: Lync Server 2013：验证外部用户连接
TOCTitle: 验证外部用户连接
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398402(v=OCS.15)
ms:contentKeyID: 49312970
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中验证外部用户连接

 

_**上一次修改主题：** 2012-10-19_

验证外部用户连接需要确保用户与访问边缘服务的服务器及端口之间的连接。

“远程连接分析器”站点 (<https://www.testocsconnectivity.com/>) 能确认您的配置，还能确认您连接、发送和接收外部用户访问需要的方案的正确消息的能力，因此是一个很有价值的资源。该站点由 Microsoft 技术支持人员进行管理和维护。若要访问远程连接分析器，请在浏览器中打开该网站并按照说明来选择方案。

## 测试外部用户和外部访问的连接

外部用户访问测试应包括贵组织支持的每种类型的外部用户，包括下列任意部分或全部用户：

  - 至少一个联盟域中的用户，然后测试 IM、状态、A/V 和桌面共享。

  - 组织支持的每个公共 IM 服务提供商的用户（其设置已完成）。

  - 匿名用户。

  - 组织内远程登录 Lync（但未使用 VPN）的用户。

这些测试确定边缘服务器是否：

  - 使用 Telnet 客户端从网络外侦听所需端口。
    
      - 示例：telnet sip.contoso.com 443
    
      - 对在边缘服务器或边缘服务器池（取决于部署情况）中使用的端口执行上述测试。

  - 执行准确的外部 DNS 解析。
    
      - 从网络外 Ping 边缘或边缘池的每个外部 FQDN。即使 Ping 失败也能查看 IP 地址，将其与已分配的地址进行比较。

