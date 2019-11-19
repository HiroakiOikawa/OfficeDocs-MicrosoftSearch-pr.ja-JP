---
title: Microsoft Search のエンタープライズ Web サイトコネクタ
ms.author: mounika.narayanan
author: monaray
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search のエンタープライズ web サイトコネクタを設定する
ms.openlocfilehash: 14eef035f4cc054ab87582b573cb6b7e3c12d0c7
ms.sourcegitcommit: 68087149c769a7cdde80944dd9c9933d2bf4a23f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699523"
---
# <a name="enterprise-websites-connector"></a><span data-ttu-id="b682e-103">エンタープライズ web サイトコネクタ</span><span class="sxs-lookup"><span data-stu-id="b682e-103">Enterprise websites connector</span></span>

<span data-ttu-id="b682e-104">エンタープライズ web サイトコネクタを使用すると、組織は**内部に接続している web サイトの**記事とコンテンツにインデックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b682e-104">With the Enterprise websites connector, your organization can index articles and **content from its internal-facing websites**.</span></span> <span data-ttu-id="b682e-105">コネクタを構成し、web サイトからコンテンツを同期すると、エンドユーザーは任意の Microsoft 検索クライアントからそのコンテンツを検索できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b682e-105">After you configure the connector and sync content from the website, end users can search for that content from any Microsoft Search client.</span></span>

<span data-ttu-id="b682e-106">この記事は、 [Microsoft 365](https://www.microsoft.com/microsoft-365)管理者またはエンタープライズ websites コネクタを構成、実行、および監視するユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="b682e-106">This article is for [Microsoft 365](https://www.microsoft.com/microsoft-365) administrators or anyone who configures, runs, and monitors an Enterprise websites connector.</span></span> <span data-ttu-id="b682e-107">コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b682e-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>  

## <a name="connect-to-a-data-source"></a><span data-ttu-id="b682e-108">データソースへの接続</span><span class="sxs-lookup"><span data-stu-id="b682e-108">Connect to a data source</span></span> 
<span data-ttu-id="b682e-109">データソースに接続するには、ルート URL と認証の形式が必要です。これには、 [Azure Active Directory (AZURE AD)](https://docs.microsoft.com/azure/active-directory/)を使用した基本認証または OAuth 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="b682e-109">To connect to your data source, you need your root URL and a form of authentication: Basic Authentication or OAuth 2.0 with [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/).</span></span>

### <a name="root-url"></a><span data-ttu-id="b682e-110">ルート URL</span><span class="sxs-lookup"><span data-stu-id="b682e-110">Root URL</span></span>
<span data-ttu-id="b682e-111">ルート URL は、クロールを開始するもので、認証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="b682e-111">The root URL is what initiates the crawl and is used for authentication.</span></span> <span data-ttu-id="b682e-112">クロールする web サイトのホームページから URL を取得できます。</span><span class="sxs-lookup"><span data-stu-id="b682e-112">You can get the URL from the home page of the website you want to crawl.</span></span>

### <a name="authentication"></a><span data-ttu-id="b682e-113">認証</span><span class="sxs-lookup"><span data-stu-id="b682e-113">Authentication</span></span> 
<span data-ttu-id="b682e-114">基本認証には、ユーザー名とパスワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="b682e-114">Basic Authentication requires a username and password.</span></span> <span data-ttu-id="b682e-115">Microsoft 365[管理センター](https://admin.microsoft.com)を使用して、この bot アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="b682e-115">Create this bot account by using the Microsoft 365 [admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="b682e-116">[AZURE AD](https://docs.microsoft.com/azure/active-directory/)を使用する OAuth 2.0 には、テナント ID、リソース ID、クライアント ID、およびクライアントシークレットが必要です。</span><span class="sxs-lookup"><span data-stu-id="b682e-116">OAuth 2.0 with [Azure AD](https://docs.microsoft.com/azure/active-directory/) requires a tenant ID, resource ID, Client ID, and Client Secret.</span></span>
<span data-ttu-id="b682e-117">詳細については、「 [OAuth 2.0 コード付与フローを使用して Azure Active Directory web アプリケーションへのアクセスを承認する](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b682e-117">For more information, see [Authorize access to Azure Active Directory web applications using OAuth 2.0 code grant flow](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code).</span></span> <span data-ttu-id="b682e-118">次の値を使用して登録します。</span><span class="sxs-lookup"><span data-stu-id="b682e-118">Register with the following values:</span></span>
* <span data-ttu-id="b682e-119">**Name:** Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="b682e-119">**Name:** Microsoft Search</span></span>
* <span data-ttu-id="b682e-120">**Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`</span><span class="sxs-lookup"><span data-stu-id="b682e-120">**Redirect_URI:** `https://gcs.office.com/v1.0/admin/oauth/callback`</span></span>

<span data-ttu-id="b682e-121">名前付きテナント、リソース、client_id、client_secret の値を取得するには、「承認コードを使用して、リダイレクト URL web ページで**アクセストークンを要求**します。</span><span class="sxs-lookup"><span data-stu-id="b682e-121">To get the values for named tenant, resource, client_id, and client_secret, go to **Use the authorization code to request an access token** on the redirect URL webpage.</span></span>

<span data-ttu-id="b682e-122">詳細については、「[クイックスタート: アプリケーションを Microsoft identity platform に登録する](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b682e-122">For even more information, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

### <a name="reverse-proxy-url"></a><span data-ttu-id="b682e-123">リバースプロキシの URL</span><span class="sxs-lookup"><span data-stu-id="b682e-123">Reverse proxy URL</span></span> 
<span data-ttu-id="b682e-124">エンタープライズ web サイトコネクタはクラウドベースであるため、オンプレミスのコンテンツにはアクセスしません。</span><span class="sxs-lookup"><span data-stu-id="b682e-124">The Enterprise websites connector is cloud-based, so it doesn't access on-premises content.</span></span> <span data-ttu-id="b682e-125">そのアクセスを提供するには、リバースプロキシをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b682e-125">To provide that access, install a reverse proxy.</span></span> <span data-ttu-id="b682e-126">リバースプロキシは、オンプレミスの web サイトへの安全で信頼できるアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b682e-126">A reverse proxy provides secure, reliable access to on-premises websites.</span></span> <span data-ttu-id="b682e-127">[Azure アプリケーションプロキシ](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b682e-127">We recommend [Azure Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span></span>

<span data-ttu-id="b682e-128">ルート URL と認証のリバースプロキシの要件は、クラウドベースのコンテンツの場合と同じですが、ルート URL と認証はリバースプロキシサーバーによって提供される点が異なります。</span><span class="sxs-lookup"><span data-stu-id="b682e-128">The reverse proxy requirement for root URL and authentication is the same as for cloud-based content, except that the root URL and authentication are provided by the reverse proxy server.</span></span>

<span data-ttu-id="b682e-129">[AZURE AD アプリケーションプロキシを使用してリモートでアプリにアクセスする場合のセキュリティに関する考慮事項を](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-security)参照してください。</span><span class="sxs-lookup"><span data-stu-id="b682e-129">See [Security considerations for accessing apps remotely with Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-security).</span></span>

## <a name="select-the-source-properties"></a><span data-ttu-id="b682e-130">ソースのプロパティを選択する</span><span class="sxs-lookup"><span data-stu-id="b682e-130">Select the source properties</span></span> 
<span data-ttu-id="b682e-131">ソースのプロパティは、エンタープライズ web サイトのデータ形式に基づいて定義されます。</span><span class="sxs-lookup"><span data-stu-id="b682e-131">Source properties are defined based on the data format of the enterprise website.</span></span> <span data-ttu-id="b682e-132">ただし、コンテンツに機密がある場合やクロール価値がない場合は、一部の Url をクロール対象から除外する除外**リスト**を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b682e-132">However, you can create an **Exclusion list** to exclude some URLs from getting crawled if that content is sensitive or not worth crawling.</span></span> <span data-ttu-id="b682e-133">除外リストを作成するには、ルート URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="b682e-133">To create an exclusion list, browse through the root URL.</span></span> <span data-ttu-id="b682e-134">構成プロセス中に、除外された Url をリストに追加するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="b682e-134">You have the option to add the excluded URLs to the list during the configuration process.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="b682e-135">検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="b682e-135">Manage search permissions</span></span> 
<span data-ttu-id="b682e-136">アクセス制御リスト (Acl) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b682e-136">There's no support for Access Control Lists (ACLs).</span></span> <span data-ttu-id="b682e-137">そのため、組織内のすべてのユーザーに表示される web サイトのみを接続することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b682e-137">Thus, we recommend connecting only the websites that are visible to any user within your organization.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="b682e-138">更新スケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="b682e-138">Set the refresh schedule</span></span>
<span data-ttu-id="b682e-139">エンタープライズ web サイトコネクタは、フルクロールのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b682e-139">The Enterprise websites connector only supports a full crawl.</span></span> <span data-ttu-id="b682e-140">これは、すべてのクロール中にコネクタがすべての web サイトのコンテンツを読み取ることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b682e-140">This means that the connector reads all the website's content during every crawl.</span></span> <span data-ttu-id="b682e-141">コネクタがコンテンツを読み取るのに十分な時間をかけるようにするには、更新のスケジュール間隔を大きくすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b682e-141">To make sure the connector gets enough time to read the content, we recommend that you set a large refresh schedule interval.</span></span> <span data-ttu-id="b682e-142">更新スケジュールは3日から2週間にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b682e-142">We recommend a scheduled refresh between three days and two weeks.</span></span>

## <a name="limitations"></a><span data-ttu-id="b682e-143">制限事項</span><span class="sxs-lookup"><span data-stu-id="b682e-143">Limitations</span></span> 
<span data-ttu-id="b682e-144">エンタープライズ web サイトコネクタは、動的 web ページ上のデータの検索をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="b682e-144">The Enterprise websites connector doesn't support searching data on dynamic webpages.</span></span> <span data-ttu-id="b682e-145">これらの web ページの例は、コンテンツ管理システム ( [Confluence](https://www.atlassian.com/software/confluence) 、 [Unily](https://www.unily.com/) 、web サイトのコンテンツを格納するデータベースなど) に存在します。</span><span class="sxs-lookup"><span data-stu-id="b682e-145">Examples of those webpages live in content management systems like [Confluence](https://www.atlassian.com/software/confluence) and [Unily](https://www.unily.com/) or databases that store website content.</span></span>