---
title: シングル サインオンのテスト
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: a220c1bf-7cee-448a-90a3-310284d03e81
description: Windows 10 ユーザーに対して Microsoft Search と Office 365 にサインインを求めるメッセージが表示される回数を減らします
ms.openlocfilehash: 9fa7e067a5d72b7044981491f8526e6de727cfae
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626893"
---
# <a name="test-single-sign-on"></a><span data-ttu-id="24f51-103">シングル サインオンのテスト</span><span class="sxs-lookup"><span data-stu-id="24f51-103">Test single sign-on</span></span>

> [!IMPORTANT]
> <span data-ttu-id="24f51-104">この記事は、Bing 管理ポータルの Microsoft Search に適用されます。</span><span class="sxs-lookup"><span data-stu-id="24f51-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="24f51-105">ポータルを Microsoft 365 管理センターに移動していますので、後で Bing ポータルの Microsoft Search は削除されます。</span><span class="sxs-lookup"><span data-stu-id="24f51-105">We’re moving the portal to the Microsoft 365 admin center, and then the Microsoft Search in Bing portal will be removed.</span></span> <span data-ttu-id="24f51-106">Microsoft 365 管理センターを使用して作業を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="24f51-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="24f51-107">[Microsoft Search の概要](overview-microsoft-search.md)。</span><span class="sxs-lookup"><span data-stu-id="24f51-107">[Overview of Microsoft Search](overview-microsoft-search.md).</span></span>
    
<span data-ttu-id="24f51-p102">シングル サインオンによって、サインインを求めるメッセージがユーザーに表示される回数を減らします。少人数のユーザー グループでシングル サインオンをテストすると、構成を妨げている問題を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="24f51-p102">Single sign-on reduces the number of times users are prompted to sign in. Testing single sign-on with a small group of users will help identify any blocking configuration issues.</span></span> 
  
<span data-ttu-id="24f51-110">Windows 10 における Chrome ユーザーの場合、シングル サインオンが機能するのは、Chrome 向けの Windows 10 と AAD サインイン拡張機能がインストールされている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="24f51-110">For Chrome users on Windows 10, single sign-on will only work if the Windows 10 and AAD sign-in extension for Chrome is installed.</span></span> 
  
## <a name="download-the-windows-10-and-aad-sign-in-extension-for-chrome"></a><span data-ttu-id="24f51-111">Chrome 向けの Windows 10 と AAD サインイン拡張機能をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="24f51-111">Download the Windows 10 and AAD sign-in extension for Chrome</span></span>

<span data-ttu-id="24f51-112">この拡張機能を自動インストールするためのグループ ポリシーを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="24f51-112">We recommend that you create a group policy to automatically install this extension.</span></span>
  
1. <span data-ttu-id="24f51-113">Microsoft Search 管理ポータルに移動します</span><span class="sxs-lookup"><span data-stu-id="24f51-113">Go to the Microsoft Search Admin portal</span></span>
    
2. <span data-ttu-id="24f51-114">ナビゲーション ウィンドウで、**[ツール]** をクリックします</span><span class="sxs-lookup"><span data-stu-id="24f51-114">In the navigation pane, click **Tools**</span></span>
    
3. <span data-ttu-id="24f51-115">ツールの一覧で、**[Chrome 向けの Windows 10 と AAD サインイン拡張機能]** をダウンロードします</span><span class="sxs-lookup"><span data-stu-id="24f51-115">In the Tools list, download the **Windows 10 and AAD sign-in extension for Chrome**</span></span>
    
4. <span data-ttu-id="24f51-116">Windows 10 の Chrome ユーザーと拡張機能を共有します</span><span class="sxs-lookup"><span data-stu-id="24f51-116">Share the extension with Chrome users on Windows 10</span></span>

  

