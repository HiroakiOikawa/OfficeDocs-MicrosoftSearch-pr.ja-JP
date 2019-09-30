---
title: Microsoft Search のセットアップ
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.date: 08/06/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search を初めてセットアップする。
ms.openlocfilehash: 3b3df3e3b3cb3e94abdf57bbb2c7e2db5f174898
ms.sourcegitcommit: 3da22a2e09830672ebf199e05a32fa89b75c083b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288993"
---
# <a name="set-up-microsoft-search"></a>Microsoft Search のセットアップ

Microsoft Search では、メール、ファイル、SharePoint ファイル、OneDrive コンテンツ、その他の共有リソース、ユーザーの組織内のインターネットを含む、すべてのデータソースに安全にアクセスすることにより、ファイルやドキュメント、内部サイトやビジネス ツール、ユーザーやグループ、場所や方向、会話や回答などの情報を検索するのに役立つユーザー フレンドリなインターフェイスを提供しています。

Microsoft Search の機能の詳細については、「[Microsoft Search の概要](overview-microsoft-search.md)」を参照してください。

## <a name="get-started"></a>はじめに

Microsoft Search は Microsoft 365 の一部であり、この機能をサポートしているすべての Microsoft アプリに対して既定で有効になっています。 ユーザーは、職場または学校のアカウントでサインインし、Bing のブラウザーを既定の検索プロバイダーとして設定するだけで、利用できます。

Microsoft Search の管理は、Microsoft 365 管理センターから行います。

1. Microsoft 365 管理センターで、[**設定**]  >  [**Microsoft Search**] の順に移動します。

**注:** [**設定**] の下に [Microsoft Search] が表示されない場合は、管理センター ページの右上隅にある [**プレビューを試す**] スイッチを有効にしてください。

管理者として、効率的でユーザー フレンドリな Microsoft Search の操作性を組織内で実現するために、いくつかの点を考慮する必要があります。

## <a name="step-1-check-access-level-of-your-users"></a>手順 1: ユーザーのアクセス レベルを確認する

Microsoft Search では、コンテンツ ソースのセキュリティ設定を尊重されます。 検索結果としてユーザーに表示される内容は、アクセス許可のレベルによって異なります。 ユーザーが、自分がアクセスを許可されているコンテンツのみを見つけるように、組織内のユーザーのアクセス レベルを確認してください。

| サービス         | 説明                                                                                                                                                                                                                                         |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| グループ          | [グループでメンバーを追加または削除する](https://docs.microsoft.com/office365/admin/create-groups/add-or-remove-members-from-groups)                                                                                                                     |
| ユーザー          | アドレス一覧で特定のユーザーが検索されないようにするには、[Set-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-user) ユーザー コマンドレットを使用して、パラメーター `HiddenFromAddressListEnabled` を `true` に設定します。 |
| Microsoft Teams | [Microsoft Teams へのユーザー アクセスを管理する](https://docs.microsoft.com/microsoftteams/user-access)                                                                                                                                                      |
| OneDrive        | [共有を管理する](https://docs.microsoft.com/OneDrive/manage-sharing)                                                                                                                                                                                |
| SharePoint      | [アクセス許可の計画](https://docs.microsoft.com/sharepoint/plan-your-permissions-strategy)<br> [アクセス許可レベルを作成する](https://docs.microsoft.com/sharepoint/how-to-create-and-edit-permission-levels)                          |
| OneNote         | OneNote に埋め込まれているファイルを検索することはできません。 [OneDrive でノートブックの権限を変更する](https://support.office.com/article/B9600CCF-045A-40E6-9913-4A7EB02869A5)                                                                    |
| Yammer          | [Yammer のセキュリティ設定](https://docs.microsoft.com/Yammer/manage-security-and-compliance/yammer-security-settings)                                                                                                                               |

## <a name="step-2-assign-search-admin-and-search-editor"></a>手順 2: 検索管理者と検索エディターを割り当てる

Microsoft Search で組織の検索設定と検索コンテンツを管理するには、ユーザーに次の役割を割り当てます。

1. **Search 管理者:** この役割では、検索結果のコンテンツを作成したり管理したりして、組織内の検索結果を向上させるためのクエリ設定を定義できます。 Search 管理者は、Microsoft Search の構成を管理し、Search エディターが実行する権限を持つコンテンツ管理タスクをすべて実行できます。
2. **Search エディター:** Microsoft 365 管理センターで Microsoft Search のコンテンツを作成、管理、および削除します。 この役割には、よく寄せられる質問や回答、重要な場所や位置、頻繁に検索および使用されるサイトやアプリなどの編集コンテンツを作成および管理する権限があります。

現時点では、検索管理者と検索エディターの役割は、全体管理者が割り当てる必要があります。詳細については、「[管理者の役割を割り当てる](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles?view=o365-worldwide)」を参照してください。

Search 管理者は、エンド ユーザーの検索エクスペリエンスに直接影響を与えます。 これには、ユーザーに表示する結果の種類の選択が含まれます。 ユーザーが組織内で検索するさまざまなトピックに対して、信頼できるコンテンツを 1 人で選択して作成するのは難しい場合があります。 内容領域専門家 (SME) や他のユーザーを検索エディターとして追加して、その専門知識や知見を活用することをお勧めします。

## <a name="step-3-make-content-easy-to-find"></a>手順 3: コンテンツを見つけやすくする

Microsoft Search では、ユーザーのために堅牢な検索環境を構築するために使用できるツールを管理者に提供しています。 Microsoft Search では、管理者がより優れた検索機能を作成し、コンテンツの見つけやすさを向上させるために、次の 3 つの検索コンテンツを使用することができます。

- **ブックマーク:** ブックマークとは、SharePoint の昇格した結果に似たもので、ユーザーのクエリに対して最適な結果を検索結果の上位に昇格させ、重要な内部サイトをユーザーが簡単に見つけられるようにします。
- **質問と回答 (Q&A):** Q&A はよく寄せられる質問 (FAQ) に似たもので、通常は質問と回答の形式です。 ユーザーの作業に関連する質問に対する最適な回答を提供します。
- **場所:** 場所とは、ユーザーが組織の建物、オフィス、キャンパスを特定するのに役立つアドレスのことです。

ブックマーク、Q&A、場所の数が増えれば増えるほど、ユーザーにとって価値が高く、利点が多いものになります。 ただし、結果を適切かつ最新の状態に保つために定期的に確認および更新する必要があるため、数が増えすぎると管理上の負担が大幅に増加してしまいます。

ユーザーのためのブックマークを考慮する必要があるコンテンツの例を次に示します。

- 組織や製品やサービスの情報。
- すべてのユーザーが利用できる情報コンテンツ。たとえば、会社に関する情報、Windows や Office アプリ用のヘルプなどです。
- 組織内ユーザーが、日常業務で検索するコンテンツ。 従業員の福利厚生、時間と経費のレポート、発注書の発行、IT サービスからのヘルプの入手など、業務関連の一般的な検索項目です。

検索コンテンツの作成と管理の詳細については、「[コンテンツを見つけやすくする](make-content-easy-to-find.md)」を参照してください。

## <a name="step-4-training-and-communication"></a>手順 4: トレーニングおよびコミュニケーション

従業員が自分で簡単にアクセスできるセルフサービスのリソースを確立します。 これにより、お客様とチームの全体的な負担を軽減し、常にコミュニケーションを促進し、従業員の自己トレーニングと教育に役立てることができます。 ユーザーのコミュニケーション、FAQ、ビデオ、録画されたトレーニングやウェビナーを提供します。 まずは、次のリンクを参考にしてください。

- [Office の Microsoft Search で必要な情報を見つける](https://support.office.com/article/find-what-you-need-with-microsoft-search-in-office-2457d4d8-48a8-4ad4-ab89-5a0657aa8446)
- [Office 365 トレーニング センター](https://support.office.com/office-training-center)
- [Microsoft Search センター](https://support.office.com/article/-working-title-microsoft-search-center-b8bf5a2c-7515-40a9-9a6a-b8ed382c86bc)