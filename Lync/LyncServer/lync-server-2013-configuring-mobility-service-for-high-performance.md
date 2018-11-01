---
title: 配置 Mobility Service 以实现高性能
TOCTitle: 配置 Mobility Service 以实现高性能
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690042(v=OCS.15)
ms:contentKeyID: 49314145
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置 Mobility Service 以实现高性能

 

_**上一次修改主题：** 2013-02-17_

在 Internet Information Services (IIS) 7.5 上安装 Lync Server 2013 Mobility Service 时，Mobility Service 安装程序会在前端服务器上配置一些性能设置。建议您使用 IIS 7.5 以实现移动功能。如果您在 Windows Server 2008 上使用 IIS 7.0，则需要手动配置这些设置。这些设置会影响 Mobility Service 允许的最大并发用户请求数和最大线程数。

以下是性能设置：

  - 将 **maxConcurrentThreadsPerCPU** 设置为零 (0)。

  - 将 **maxConcurrentRequestsPerCPU** 设置为零 (0)。

  - 将 ASP.NET 进程模型设置为 AutoConfig（仅针对 IIS 7.5）。

  - 将 HTTP.sys 队列限制设置为 1,000（默认值）。

如果您使用的是 IIS 7.0，建议您安装可从 Microsoft 知识库文章 2290617“修复：用于为 IIS 7.0 中的每个应用程序池配置一些 ASP.NET 属性的修补程序现已发布”（网址为 [http://go.microsoft.com/fwlink/?linkid=3052\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=3052%26clcid=0x804)）中获得的更新，以便您能够只将更改应用于 Mobility Service 而不会影响其他 Web 服务。

以下过程介绍，在您尚未安装来自知识库文章 2290617 的更新的情况下，如何更改 IIS 7.0 上的 ASP.NET 并发请求数和线程数的最大值。但是，即使您安装了来自知识库文章 2290617 的更新，您也应使用该文章提供的文档以仅对移动功能的内部和外部 IIS 应用程序池应用相同的更改。在此情况下，可以对 ASP.NET 设置使用单独的配置文件。

> [!IMPORTANT]
> 如果使用以下过程来更改最大值，则所做的更改将影响所有 IIS 应用程序池。


有关配置这些设置的详细信息，请参阅 [http://go.microsoft.com/fwlink/?linkid=234537\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=234537%26clcid=0x804)。

## 更改并发请求数和线程数的最大值

1.  单击“开始”，再单击“运行”。

2.  在“运行”框中键入：
    
        notepad %SystemRoot%\Microsoft.NET\Framework64\v2.0.50727\Aspnet.config

3.  单击“确定”。

4.  在 Aspnet.config 文件中，将以下 \<system.web\> 元素作为 \<configuration\> 元素的子元素来添加或替换：
    
        <system.web>
        <applicationPool maxConcurrentRequestsPerCPU="<#>" maxConcurrentThreadsPerCPU="0" requestQueueLimit="5000"/>
        </system.web>
    
    其中，\# 为 0（表示删除限制）或本节前面所述的新数字。

5.  保存 Aspnet.config 文件并关闭“记事本”。

