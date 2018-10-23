---
title: 还原响应组设置
TOCTitle: 还原响应组设置
ms:assetid: 4f8e1949-925d-4538-be1d-9ac7c06b2aca
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh202174(v=OCS.15)
ms:contentKeyID: 52061022
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 还原响应组设置

 

_**上一次修改主题：** 2013-02-18_

如果您部署了响应组应用程序且需要还原后端服务器或 Standard Edition Server，则还需要还原响应组配置设置。

## 还原响应组配置设置

1.  在命令行中键入：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<pool FQDN>" -OverwriteOwner -FileName "<path and file name of the backed up file at $Backup>"
    
    例如：
    
        Import-CsRgsConfiguration -Destination "service: ApplicationServer:pool01.contoso.com" -OverwriteOwner -FileName "C:\RgsConfiguration.zip"

