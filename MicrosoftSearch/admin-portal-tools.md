---
title: 管理ポータルのツール
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 4a824483-2407-4bbd-8f7f-5ebb47817c7e
ROBOTS: NoIndex
description: 結果を作成したりインポートしたり、自動的にサインインしたり、どこからでも検索したりできるようにする Microsoft Search ツールの概要
ms.openlocfilehash: 16beaf5ae2945df19b32b65ae4e65b4989217f9f
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591352"
---
# <a name="admin-portal-tools"></a><span data-ttu-id="ec788-103">管理ポータルのツール</span><span class="sxs-lookup"><span data-stu-id="ec788-103">Admin portal tools</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ec788-104">この記事は、Bing 管理ポータルの Microsoft Search に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ec788-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="ec788-105">ポータルを Microsoft 365 管理センターに移動しており、後で削除されます。</span><span class="sxs-lookup"><span data-stu-id="ec788-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="ec788-106">Microsoft 365 管理センターを使用して作業を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ec788-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="ec788-107">[Microsoft Search の概要](overview-microsoft-search.md)。</span><span class="sxs-lookup"><span data-stu-id="ec788-107">Overview of Microsoft Search</span></span>
    
<span data-ttu-id="ec788-108">Microsoft Search 管理ポータルには、管理者、編集者、ユーザーのために設計されたツールやリソースが含まれています。以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ec788-108">The Microsoft Search Admin portal includes tools and resources designed for admins, editors, and users, including:</span></span>
  
- <span data-ttu-id="ec788-109">コンテンツ作成者のブラウザー拡張機能</span><span class="sxs-lookup"><span data-stu-id="ec788-109">Content creator browser extension</span></span>
    
    <span data-ttu-id="ec788-110">管理者と編集者が使用できます。Chrome または Edge の拡張機能を使用して、サイトまたはページに移動するだけで、簡単に[ブックマーク](create-bookmarks.md)や [Q & A](create-qas.md) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ec788-110">Available for admins and editors, use the Chrome or Edge extension to easily [create bookmarks](create-bookmarks.md) and [Q&As](create-qas.md) simply by going to a site or page.</span></span> 
    
- <span data-ttu-id="ec788-111">Bing 検索での Microsoft Search の拡張機能</span><span class="sxs-lookup"><span data-stu-id="ec788-111">Microsoft Search in Bing search extension</span></span>
    
    <span data-ttu-id="ec788-112">ChromeまたはEdgeの拡張機能を使用して、アクセスしているページやサイトから離れずにMicrosoft Searchのエンタープライズ検索にすばやくアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ec788-112">Use the Chrome or Edge extension to quickly access Microsoft Search enterprise search without leaving the page or site you're on.</span></span>
    
- <span data-ttu-id="ec788-113">Windows 10 と AAD サインインのためのChrome 拡張機能</span><span class="sxs-lookup"><span data-stu-id="ec788-113">Windows 10 and AAD sign-in extension for Chrome</span></span>
    
    <span data-ttu-id="ec788-114">Office 365やBingなどのサポートされているサイトにサインインするときに、Chrome拡張機能を使用してAzure Active Directoryで簡単に認証します。</span><span class="sxs-lookup"><span data-stu-id="ec788-114">Use the Chrome extension to easily authenticate with Azure Active Directory when signing in to supported sites, including Office 365 and Bing.</span></span> <span data-ttu-id="ec788-115">[シングル サインオンをテスト](test-single-sign-on.md)する場合は、この拡張機能を展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ec788-115">We recommend deploying this extension when you [test single sign-on](test-single-sign-on.md).</span></span>
    
- <span data-ttu-id="ec788-116">ブックマークとしてよく使用される SharePoint クエリをインポートする</span><span class="sxs-lookup"><span data-stu-id="ec788-116">Import top SharePoint queries as bookmarks</span></span>
    
    <span data-ttu-id="ec788-p103">管理者が使用できます。この PowerShell スクリプトを使用して、ドラフト ブックマークとして [SharePoint のよく使用されるクエリをインポートする](import-sharepoint-promoted-results-and-top-queries.md)ことができます。スクリプトをダウンロードして、要件、サンプル、使用可能なパラメーターについて README ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ec788-p103">Available to admins, use this PowerShell script to [import SharePoint top queries](import-sharepoint-promoted-results-and-top-queries.md) as draft bookmarks. Download the script and open the README file for information about requirements, examples, and available parameters.</span></span> 
    
- <span data-ttu-id="ec788-119">ブックマークとして SharePoint の昇格結果クエリ ルールをインポートする</span><span class="sxs-lookup"><span data-stu-id="ec788-119">Import SharePoint Promoted Result Query Rules as bookmarks</span></span>
    
    <span data-ttu-id="ec788-120">管理者が使用できます。おすすめのブックマークとして、[SharePoint の昇格結果](import-sharepoint-promoted-results-and-top-queries.md)、よく使用されるクエリ、またはおすすめコンテンツをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ec788-120">Available to admins, [import SharePoint promoted results](import-sharepoint-promoted-results-and-top-queries.md) and top queries, or Best Bets, as suggested bookmarks.</span></span> 

  

