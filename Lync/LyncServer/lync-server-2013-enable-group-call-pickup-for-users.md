---
title: 为用户启用组内呼叫应答
TOCTitle: 为用户启用组内呼叫应答
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945620(v=OCS.15)
ms:contentKeyID: 52060976
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为用户启用组内呼叫应答

 

_**上一次修改主题：** 2013-01-30_

使用 SEFAUtil 资源工具包工具为用户启用组内呼叫应答。必须在呼叫寄存通道表中为用户分配一个具有 GroupPickup 类型的组内号码，以便启用组内呼叫应答。在运行 SEFAUtil.exe 时，通过使用 /enablegrouppickup 参数，可同时分配呼叫应答组内号码和启用组内呼叫应答。

## 为用户启用组内呼叫应答

1.  使用管理员权限登录已安装 SEFAUtil 工具的计算机。

2.  在命令行处，运行：
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    例如：
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

## 另请参阅

#### 任务

[向用户分配组内呼叫应答号码](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[为用户禁用组内呼叫应答](lync-server-2013-disable-group-call-pickup-for-users.md)

