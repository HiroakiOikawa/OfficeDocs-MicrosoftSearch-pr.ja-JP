---
title: 高度な DNS 構成
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/19/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MOE150
- MED150
ms.assetid: 47eedbb9-6da9-47e0-aac5-078d34a7fd8f
ROBOTS: NoIndex
description: CNAME を使用して DNS サーバーを構成することにより、ユーザーがシームレスなサインイン エクスペリエンスを利用できるようにします
ms.openlocfilehash: 6a291165df33f8acc99d247104e8e88cd35c3a0e
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591361"
---
# <a name="advanced-dns-configuration"></a>高度な DNS 構成

> [!IMPORTANT]
> この記事は、Bing 管理ポータルの Microsoft Search に適用されます。 ポータルを Microsoft 365 管理センターに移動しており、後で削除されます。 Microsoft 365 管理センターを使用して作業を開始することをお勧めします。 [Microsoft Search の概要](overview-microsoft-search.md)。
    
Bing で組織内のユーザーを特定し、ユーザーが職場または学校のアカウントに正常にサインインできるようにするには、内部 DNS サーバーまたはプロキシを構成し、`www.bing.com` から `ms.bing.com` に解決できるようにします。そのためには、`ms.bing.com` の CNAME となるように `www.bing.com` の DNS エントリを作成します。
  
****

|**名前**|**Type**|**値**|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |CNAME  <br/> |`ms.bing.com`  <br/> |
   
IP アドレスではなく CNAME を使用する方が推奨されているのは、IP アドレスが変更した場合であっても CNAME は引き続き機能するためです。このように DNS を変更すると、ユーザーが `www.bing.com` からアクセスする場合でも結果が表示されます。 
  
この場合、クライアント マシンで追加構成は必要なく、ユーザーにシームレスはエクスペリエンスを提供できます。ユーザーが `bing.com` にアクセスすると、一貫性のある方法で自動的にサインインできます。自動的にサインインできない場合には、サインインするようメッセージが表示されます。
