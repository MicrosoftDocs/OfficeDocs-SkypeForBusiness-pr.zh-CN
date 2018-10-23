---
title: Lync Server 2013：在边缘服务器上部署 IP 地址类型
TOCTitle: 在边缘服务器上部署 IP 地址类型
ms:assetid: 6e2fe7e8-6e90-4d1a-8fc5-e3be92c46571
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204984(v=OCS.15)
ms:contentKeyID: 49313176
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 边缘服务器上部署 IP 地址类型

 

_**上一次修改主题：** 2012-06-14_

使用 拓扑生成器执行以下过程中的步骤，以便在 边缘服务器上部署 IP 地址类型。

## 在边缘服务器上部署 IP 地址类型

1.  在 拓扑生成器中的“边缘池”下，右键单击池中的服务器，然后选择“编辑属性”。（也可以选择服务器并从“操作”菜单中单击“编辑属性”。）

2.  在“编辑属性”窗口中，选择要支持的 IP 地址配置。下图显示用于内部接口和外部接口的双协议栈配置。
    
    **双协议栈边缘服务器内部接口**
    
    ![Lync Server 常规属性页](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Lync Server 常规属性页")
    
    **双协议栈边缘服务器外部接口**
    
    ![Lync Server 下一个跃点/外部配置页面](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server 下一个跃点/外部配置页面")

3.  对于您选择的每个地址类型，必须提供适当的内部和外部地址。

