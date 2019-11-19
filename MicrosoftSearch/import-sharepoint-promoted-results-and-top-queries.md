---
title: SharePoint の昇格した結果および上位のクエリのインポート
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 3d2a1498-174e-4214-9cf1-8b58cce5a872
ROBOTS: NOINDEX
description: SharePoint からの検索クエリを使用して Microsoft Search の作業結果を作成する
ms.openlocfilehash: ae3535e322c4d06505595018669d8bd87171b9a9
ms.sourcegitcommit: 68087149c769a7cdde80944dd9c9933d2bf4a23f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699873"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="d1d66-103">SharePoint の昇格した結果および上位のクエリのインポート</span><span class="sxs-lookup"><span data-stu-id="d1d66-103">Import SharePoint promoted results and top queries</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1d66-104">この記事は、Bing 管理ポータルの Microsoft Search に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d1d66-104">This article applies to the Microsoft Search in the Bing admin portal.</span></span> <span data-ttu-id="d1d66-105">ポータルを Microsoft 365 管理センターに移動していますので、後で Bing ポータルの Microsoft Search は削除されます。</span><span class="sxs-lookup"><span data-stu-id="d1d66-105">We’re moving the portal to the Microsoft 365 admin center, and then the Microsoft Search in Bing portal will be removed.</span></span> <span data-ttu-id="d1d66-106">Microsoft 365 管理センターを使用して作業を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d1d66-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="d1d66-107">[Microsoft Search の概要](overview-microsoft-search.md)。</span><span class="sxs-lookup"><span data-stu-id="d1d66-107">[Overview of Microsoft Search](overview-microsoft-search.md).</span></span>
    
<span data-ttu-id="d1d66-108">SharePoint で作成したユーザーのクエリとおすすめコンテンツを活用するために、Microsoft Search には、この情報を提案されたブックマークとしてインポートするためのツールが2つ含まれています。</span><span class="sxs-lookup"><span data-stu-id="d1d66-108">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="d1d66-109">SharePoint で昇格した結果のクエリルールをインポートする</span><span class="sxs-lookup"><span data-stu-id="d1d66-109">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="d1d66-110">推奨されるブックマークとして、これらのルール (以前のおすすめコンテンツ) をインポートします。</span><span class="sxs-lookup"><span data-stu-id="d1d66-110">Import these rules, previously called Best Bets, as suggested bookmarks.</span></span> <span data-ttu-id="d1d66-111">それらをユーザーが使用できるようにするには、それらを公開します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-111">To make them available to your users, publish them.</span></span> <span data-ttu-id="d1d66-112">公開時間は、選択したブックマークの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d1d66-112">Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="d1d66-113">PowerShell を使用してトップの SharePoint クエリをインポートする</span><span class="sxs-lookup"><span data-stu-id="d1d66-113">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="d1d66-114">SharePoint から上位のクエリをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d1d66-114">Download the top queries from your SharePoint.</span></span> <span data-ttu-id="d1d66-115">PowerShell スクリプトでは、SharePoint 管理者の資格情報の入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="d1d66-115">The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="d1d66-116">上位の検索結果を取得するには、上位の各クエリに対して SharePoint 検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-116">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="d1d66-117">管理ポータルに推奨されるブックマークを追加します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-117">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="d1d66-118">SharePoint の上位のクエリは、ブックマークを作成するのに適しています。</span><span class="sxs-lookup"><span data-stu-id="d1d66-118">Your top SharePoint queries are excellent candidates for bookmarks.</span></span> <span data-ttu-id="d1d66-119">PowerShell スクリプトを使用して、提案されたブックマークとしてインポートします。</span><span class="sxs-lookup"><span data-stu-id="d1d66-119">Use the PowerShell script to import them as suggested bookmarks.</span></span> <span data-ttu-id="d1d66-120">このスクリプトは、次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="d1d66-120">This script does the following work:</span></span>
    - <span data-ttu-id="d1d66-121">SharePoint の上位のクエリに基づいて、Microsoft 検索ブックマークの範囲を向上させるために推奨されるブックマークを追加します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-121">Adds suggested bookmarks based on SharePoint top queries to improve Microsoft Search bookmark coverage.</span></span> <span data-ttu-id="d1d66-122">このスクリプトは、SharePoint 管理ポータルからアクセス可能な上位のクエリをダウンロードし、次に Microsoft 検索管理ポータルでレビューするための管理者のために推奨されるブックマークとしてアップロードします。</span><span class="sxs-lookup"><span data-stu-id="d1d66-122">This script downloads the top queries accessible from SharePoint admin portal, and then uploads them as suggested bookmarks for an admin to review in the Microsoft Search admin portal.</span></span>
    - <span data-ttu-id="d1d66-123">既定では、スクリプトは、使用可能なすべての月の指定されたテナントに提案されたブックマークを追加します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-123">By default, the script adds suggested bookmarks to given tenant for all available months.</span></span> <span data-ttu-id="d1d66-124">このメソッドは、指定された SharePoint 管理者 web サイトから上位のクエリを取得し、提案されたブックマークとして Microsoft Search に追加します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-124">It gets top queries from a given SharePoint admin website and adds them to Microsoft Search as suggested bookmarks.</span></span> <span data-ttu-id="d1d66-125">推奨されるブックマークは、公開する前に管理者ポータルで権限を付与するための管理者/編集者を必要とします。</span><span class="sxs-lookup"><span data-stu-id="d1d66-125">Suggested bookmarks need an admin/editor to approve them in the admin portal before being published.</span></span> <span data-ttu-id="d1d66-126">このスクリプトを実行すると、Microsoft Search 管理ポータルにアクセスするための資格情報を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1d66-126">When you run this script, you are prompted for credentials to access the Microsoft Search admin portal.</span></span>
    - <span data-ttu-id="d1d66-127">このスクリプトでは、追加のパラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d1d66-127">The script allows additional parameters to be specified.</span></span> <span data-ttu-id="d1d66-128">たとえば、使用可能な各月の top N クエリに対して、指定したテナントに提案されたブックマークを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="d1d66-128">You can, for example, add suggested bookmarks to given tenant for top N queries in each of the available months.</span></span>
    - <span data-ttu-id="d1d66-129">必要に応じて、指定した年の月に対して、指定したテナントに提案されたブックマークを追加できます。</span><span class="sxs-lookup"><span data-stu-id="d1d66-129">Optionally, you can add suggested bookmarks to given tenant for months in the given year.</span></span> <span data-ttu-id="d1d66-130">このコマンドは、指定された期間のクエリを SharePoint 管理者 web サイトから取得し、提案されたブックマークとして Microsoft Search に追加します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-130">This command gets top queries for the given time period from SharePoint admin website and adds them to Microsoft Search as suggested bookmarks.</span></span>
    - <span data-ttu-id="d1d66-131">その他にも、多くのオプションとコマンドモードがあります。 SharePoint から指定されたフォルダーに上位クエリをダウンロードし、スクリプトをセーフモードで実行し、詳細モードでスクリプトを実行し、デバッグモードにします。</span><span class="sxs-lookup"><span data-stu-id="d1d66-131">As well, there are numerous other options and command modes: download top queries from SharePoint to a specified folder, run the script in Safe mode, run the script in Verbose mode, and a Debug mode.</span></span>
    - <span data-ttu-id="d1d66-132">[この](https://www.bingforbusiness.com/distribution/SharepointTopQueryBookmarks.zip)スクリプトをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d1d66-132">Download the script [here](https://www.bingforbusiness.com/distribution/SharepointTopQueryBookmarks.zip).</span></span> 

<span data-ttu-id="d1d66-133">要件、例、および使用可能なパラメーターの詳細については、スクリプトをダウンロードし、README ファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1d66-133">For information about requirements, examples, and available parameters, download the script and review the README file.</span></span> <span data-ttu-id="d1d66-134">PowerShell スクリプトを実行した後、管理者または編集者は、提案されているブックマークを確認して、公開する前に必要な編集を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1d66-134">After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>