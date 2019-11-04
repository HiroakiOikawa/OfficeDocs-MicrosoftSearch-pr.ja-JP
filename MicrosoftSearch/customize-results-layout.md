---
title: 検索結果のレイアウトをカスタマイズする
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: アダプティブカードを使用して、カスタマイズされた検索結果を表示するレイアウトを作成する
ms.openlocfilehash: 2ca53f2e2dc207acdf48542f39ee4f448bdeb90e
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949911"
---
# <a name="create-a-layout-to-customize-search-results"></a><span data-ttu-id="61aed-103">レイアウトを作成して検索結果をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="61aed-103">Create a layout to customize search results</span></span>

<span data-ttu-id="61aed-104">検索レイアウトデザイナーを使用して、カスタム縦の結果レイアウトを設計できます。</span><span class="sxs-lookup"><span data-stu-id="61aed-104">You can design the result layout for a custom vertical using the search layout designer.</span></span> <span data-ttu-id="61aed-105">レイアウトの設計を開始するには、レイアウトデザイナーで提供されているテンプレートを選択し、要件に適合している場合はそのテンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="61aed-105">You can start designing the layout by choosing templates offered in the layout designer and using them if they fit your requirements.</span></span> <span data-ttu-id="61aed-106">また、必要に応じてさまざまな方法でテンプレートを編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="61aed-106">Or you can choose to edit these templates in various ways to fit your requirements.</span></span> <span data-ttu-id="61aed-107">たとえば、画像の追加または削除、テキストの追加と削除、テキストの変更を行います。</span><span class="sxs-lookup"><span data-stu-id="61aed-107">For example, add/remove images, add/remove text, modify text.</span></span> <span data-ttu-id="61aed-108">要件を満たすテンプレートがない場合は、空白のテンプレートを使用してレイアウトの設計を開始することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="61aed-108">If none of the templates meet your requirement, you can choose to start designing your layout using a blank template.</span></span>  

 

<span data-ttu-id="61aed-109">レイアウトの準備が整ったら、[アダプティブカードテンプレート言語](https://docs.microsoft.com/adaptive-cards/templating/language)を使用して、結果の種類を定義するために使用される結果レイアウト JSON を作成します。</span><span class="sxs-lookup"><span data-stu-id="61aed-109">Once the layout is ready, you use the [Adaptive Cards Template language](https://docs.microsoft.com/adaptive-cards/templating/language)  to create thea result layout JSON which is used to define a result type.</span></span> <span data-ttu-id="61aed-110">レイアウトデザイナーのマッピング手順を使用して、結果のプロパティをレイアウトにマップします。</span><span class="sxs-lookup"><span data-stu-id="61aed-110">You map the result properties to the layout using the Mapping step in the layout designer.</span></span>  

## <a name="create-a-layout-on-your-own"></a><span data-ttu-id="61aed-111">独自のレイアウトを作成する</span><span class="sxs-lookup"><span data-stu-id="61aed-111">Create a layout on your own</span></span>
<span data-ttu-id="61aed-112">独自にレイアウトを作成するには、[アダプティブカード](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started)とその[スキーマ](https://adaptivecards.io/explorer/)についての知識が必要です。</span><span class="sxs-lookup"><span data-stu-id="61aed-112">Creating a layout on your own requires knowledge of [adaptive cards](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started) and their [schema](https://adaptivecards.io/explorer/).</span></span> <span data-ttu-id="61aed-113">検索結果のレイアウトでは、アダプティブカードで提供される要素のサブセットを使用し、レイアウトデザイナーを使用して、サポートされている要素のセットを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="61aed-113">Search result layout uses a subset of the elements offered by adaptive cards and you can use the layout designer to learn about the supported set of elements.</span></span>  

<span data-ttu-id="61aed-114">独自のレイアウトを作成するときに、からデータを使用してアダプティブカードレイアウトを作成し、レイアウトを確定します。</span><span class="sxs-lookup"><span data-stu-id="61aed-114">While creating your own layout, create the adaptive card layout using data from your , and then finalize the layout.</span></span>
<span data-ttu-id="61aed-115">独自のレイアウトを作成するには、2つの主要な手順があります。</span><span class="sxs-lookup"><span data-stu-id="61aed-115">There are two main steps in creating your own layout</span></span>
- <span data-ttu-id="61aed-116">レイアウトの設計</span><span class="sxs-lookup"><span data-stu-id="61aed-116">Designing the layout</span></span>
- <span data-ttu-id="61aed-117">テンプレートからのデータの分離</span><span class="sxs-lookup"><span data-stu-id="61aed-117">Separating the data from the template</span></span>

#### <a name="designing-the-layout"></a><span data-ttu-id="61aed-118">レイアウトの設計</span><span class="sxs-lookup"><span data-stu-id="61aed-118">Designing the layout</span></span>

<span data-ttu-id="61aed-119">この例では、ヘッダー、リンク、および説明のテキストを含むレイアウトを表示しています。</span><span class="sxs-lookup"><span data-stu-id="61aed-119">In this example, we're showing a layout with a header, link, and descriptive text.</span></span>

![ヘッダー、リンク、および説明を含むレイアウトの例です。](media/Verts-ExampleLayout.png)

<span data-ttu-id="61aed-121">レイアウトに関連付けられている JSON ファイルは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="61aed-121">And here's the layout's associated JSON file:</span></span>


```json
{ 
    "type": "AdaptiveCard", 
    "version": "1.0", 
     "body": [ 
{ 

            "type": "ColumnSet", 
             "columns": [ 
                 { 
                     "type": "Column", 
                     "width": 8, 
                     "items": [ 
                         { 
                             "type": "TextBlock", 
                             "text": "Contoso Marketing Analysis - Q3 FY18", 
                             "color": "Accent", 
                             "size": "Medium", 
                             "spacing": "None", 
                             "$when": "{title != \"\"}", 
                             "weight": "Bolder" 
                        }, 
                        { 
                        "type": "TextBlock",  
                        "text": "https://contoso.com/hr/link", 
                        "spacing": "None",  
                        "color": "Dark", 
                        "weight": "Bolder" 

                        }, 

                        {  
                        "type": "TextBlock", 
                        "text": "Marketing team at Contoso.., and looking at the Contoso Marketing documents on the team site. This contains the data from FY20 and will taken over to FY21...Marketing Planning is ongoing for FY20..",  
                        "wrap": true, 
                        "maxLines": 2, 
                        "spacing": "Medium" 
                        } 
                        ], 

                    "horizontalAlignment": "Center", 
                    "spacing": "None" 

                } 

            ] 

        } 
        ], 

    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json" 
}
```

#### <a name="separating-the-data-from-the-layout"></a><span data-ttu-id="61aed-122">データをレイアウトから分離する</span><span class="sxs-lookup"><span data-stu-id="61aed-122">Separating the data from the layout</span></span>

<span data-ttu-id="61aed-123">データをレイアウトから分離し、データをバインドすることができます。</span><span class="sxs-lookup"><span data-stu-id="61aed-123">You can separate the data from the layout and bind the data.</span></span> 

<span data-ttu-id="61aed-124">データをバインドした後のレイアウト JSON を次に示します。</span><span class="sxs-lookup"><span data-stu-id="61aed-124">Here's Layout JSON after binding the data:</span></span>


```json
{ 

    "type": "AdaptiveCard", 
    "version": "1.0", 
    "body": [ 
    { 
    "type": "ColumnSet", 
"columns": [ 

                { 
                "type": "Column", 
                "width": 8, 
                "items": [ 
                { 
                "type": "TextBlock", 
                "text": "[{title}]({titleUrl})", 
                "color": "Accent", 
                "size": "Medium",
                "spacing": "None", 
                "weight": "Bolder" 

                 }, 
                 { 
                 "type": "TextBlock", 
                 "text": "{link}",
                 "spacing": "None", 
                 "color": "Dark",
                 "weight": "Bolder" 
                 }, 
                 { 
                 "type": "TextBlock",
                 "text": "{description}",
                 "wrap": true,
                 "maxLines": 2, 
                 "spacing": "Medium" 
                 } 
                 ], 
                 "horizontalAlignment": "Center", 
                 "spacing": "None" 
                 } 
                 ] 

        } 

    ], 

    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json" 
}
```

<span data-ttu-id="61aed-125">サンプルデータ: サンプルデータ**エディター**でサンプルデータを指定して、[プレビューモード] のときにデータバインドカードを表示します。</span><span class="sxs-lookup"><span data-stu-id="61aed-125">Sample data: Specify sample data in the **Sample Data Editor** to view the data-bound card when in "Preview Mode".</span></span>

```json
{ 

    "title": "Contoso Marketing Analysis - Q3 FY18", 
    "titleUrl": "https://contoso.com/hr/link", 
    "link": "https://contoso.com/hr/link", 
    "description": "Marketing team, and looking at the Contoso Marketing documents on the team site. Yo can't see right...Marketing Planning presentation?" 

} 
```

## <a name="map-the-layout-to-the-result-properties"></a><span data-ttu-id="61aed-126">レイアウトを結果プロパティにマップする</span><span class="sxs-lookup"><span data-stu-id="61aed-126">Map the layout to the result properties</span></span>

<span data-ttu-id="61aed-127">結果レイアウト JSON を生成するには、レイアウトの各フィールドを result プロパティまたは connector プロパティにマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="61aed-127">You must map each field of the layout to a result property or a connector property to generate the result layout JSON.</span></span>

![Verts-SearchLayoutDesigner](media/Verts-SearchLayoutDesigner.png)

<span data-ttu-id="61aed-129">レイアウト内のフィールドを選択して、マップする必要がある変数を強調表示にします。</span><span class="sxs-lookup"><span data-stu-id="61aed-129">Select a field in the layout to highlight the variables that need to be mapped.</span></span> <span data-ttu-id="61aed-130">1つのフィールドに複数の変数を使用することができます。また、すべてのフィールドを result プロパティにマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="61aed-130">You can use multiple variables for a single field and all fields must be mapped to the result properties.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="61aed-131">検討事項</span><span class="sxs-lookup"><span data-stu-id="61aed-131">Things to consider...</span></span>

<span data-ttu-id="61aed-132">開始する前に、レイアウトが正常に機能するようにするために、いくつかの作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="61aed-132">Before you get started, there are a few things that you should do and a few things you should avoid to ensure that your layouts will be successful.</span></span>

### <a name="do"></a><span data-ttu-id="61aed-133">するべきこと</span><span class="sxs-lookup"><span data-stu-id="61aed-133">Do</span></span>

- <span data-ttu-id="61aed-134">ロゴに対して静的なリンクを使用していて、結果のプロパティではない場合は、テンプレートを編集して、レイアウトにロゴのリンクを表示します。</span><span class="sxs-lookup"><span data-stu-id="61aed-134">Edit a template to provide the logo link in the layout if you are using static links for logos and not result properties.</span></span>   
- <span data-ttu-id="61aed-135">Result のレイアウトを検証します。結果の JSON で使用される result プロパティのデータが返されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="61aed-135">Validate the result layout for scenarios where no data is returned for a result property used in the result JSON.</span></span> <span data-ttu-id="61aed-136">プロパティ`$when`にデータが含まれていない場合は、条件を使用して要素を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="61aed-136">Use `$when` condition to hide an element if the property doesn't contain data.</span></span>  
- <span data-ttu-id="61aed-137">`$when`条件のデータ型と result プロパティが一致していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="61aed-137">Make sure that data types of the `$when` condition and the result property match.</span></span> <span data-ttu-id="61aed-138">たとえば、in `Number` `Text` `$when`条件と比較しないでください。</span><span class="sxs-lookup"><span data-stu-id="61aed-138">For example, don't compare `Number` with `Text` in `$when` condition.</span></span>  
- <span data-ttu-id="61aed-139">結果のレイアウトを設計するときは、テーマの要件を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="61aed-139">Think of theme requirements when designing a result layout.</span></span>  
- <span data-ttu-id="61aed-140">要素が動的`Textblock`コンテンツを処理できることを確認してください。  </span><span class="sxs-lookup"><span data-stu-id="61aed-140">Make sure that `Textblock` element can handle dynamic content.</span></span> <span data-ttu-id="61aed-141">この目的には`wrap` 、 `maxLines`および要素のプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="61aed-141">You can use the `wrap` and `maxLines` element properties for this purpose.</span></span> 
- <span data-ttu-id="61aed-142">Markdown で使用`{DATE()}`するときに、日付を適切に書式設定します。</span><span class="sxs-lookup"><span data-stu-id="61aed-142">Properly format the date when using `{DATE()}` in markdown.</span></span>  

### <a name="dont"></a><span data-ttu-id="61aed-143">してはいけないこと</span><span class="sxs-lookup"><span data-stu-id="61aed-143">Don't</span></span>

- <span data-ttu-id="61aed-144">値をバインドするときは、無効なデータ型を定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="61aed-144">Don't define invalid data types when binding values.</span></span> <span data-ttu-id="61aed-145">データ型の詳細については、「 [Manage The Search schema](https://docs.microsoft.com/sharepoint/search/manage-the-search-schema )」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61aed-145">For more information about the data types, see [Manage the Search schema](https://docs.microsoft.com/sharepoint/search/manage-the-search-schema ).</span></span>
- <span data-ttu-id="61aed-146">結果レイアウト JSON の最大の高さに従って、結果ページ上の結果をトリミングしないようにします。</span><span class="sxs-lookup"><span data-stu-id="61aed-146">Avoid cropping the result on the result page by following the maximum height of the result layout JSON.</span></span> <span data-ttu-id="61aed-147">結果レイアウトの高さの最大値を超えると、結果ページに結果がトリミングされます。</span><span class="sxs-lookup"><span data-stu-id="61aed-147">If you exceed the maximum height of the result layout the result will be cropped on the result page.</span></span>
- <span data-ttu-id="61aed-148">要素の`px`プロパティで値を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="61aed-148">Don't use `px` values in properties of element.</span></span>


## <a name="resources"></a><span data-ttu-id="61aed-149">リソース</span><span class="sxs-lookup"><span data-stu-id="61aed-149">Resources</span></span>
[<span data-ttu-id="61aed-150">検索結果ページをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="61aed-150">Customize search result page</span></span>](customize-search-page.md)

[<span data-ttu-id="61aed-151">アダプティブカード</span><span class="sxs-lookup"><span data-stu-id="61aed-151">Adaptive cards</span></span>](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started)

[<span data-ttu-id="61aed-152">アダプティブカードテンプレートの言語</span><span class="sxs-lookup"><span data-stu-id="61aed-152">Adaptive Cards Template language</span></span>](https://docs.microsoft.com/adaptive-cards/templating/language)

[<span data-ttu-id="61aed-153">アダプティブカードスキーマ</span><span class="sxs-lookup"><span data-stu-id="61aed-153">Adaptive card schema</span></span>](https://adaptivecards.io/explorer/)
