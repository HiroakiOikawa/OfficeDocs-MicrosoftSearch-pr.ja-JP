---
title: コネクタのプレビュー
ms.author: mounika.narayanan
author: monaray
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search の Microsoft Graph コネクタプレビューに関する情報を確認します。
ms.openlocfilehash: 4bcd8360957be69bc701e8b356cd222de32bfc5f
ms.sourcegitcommit: 64eea81f8c1db9ee955013462a7b51612fb7d0b7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "44604385"
---
# <a name="microsoft-graph-connectors-preview"></a>Microsoft Graph コネクタのプレビュー

Microsoft Graph のコネクタと Microsoft Search Api (クエリとインデックス) は現在プレビュー状態になっています。 コネクタ機能へのアクセスを取得するには、テナントで対象のリリースオプションをオンにする必要があります。 これは初期のプレビューであり、サービスレベルの保証はありません。 お客様には、コネクタの機能を試してフィードバックを提供することをお勧めします。 プレビュー期間中は、運用のためにコネクタを使用することはお勧めしません。

## <a name="set-up-targeted-release"></a>対象となるリリースのセットアップ

コネクタを試行するには、組織内のすべてのユーザーに対して**対象となるリリース**オプションが設定されている必要があります。 対象となるリリースオプションの詳細と設定方法については、「 [Office 365 で標準または対象指定リリースオプションを設定](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)する」を参照してください。

## <a name="choose-a-preview-environment"></a>プレビュー環境を選択する

コネクタ、インデックス Api、および検索 Api を試すには、次の2つの方法をお勧めします。

1. **テナントをテスト**します。  テストテナントを使用して、Microsoft Graph コネクタのプレビューを試してみることをお勧めします。

2. **サイトコレクションをテスト**します。 テストテナントがない場合は、テストサイトコレクションを作成してコネクタ機能を試すことができます。 組織内の他の場所にある検索ページに影響を及ぼさずに、コネクタからの結果を表示するには、そのサイトコレクションの検索機能のみをカスタマイズします。

## <a name="preview-limitations"></a>プレビューの制限事項

プレビューリリースには、次の制限があります。

* 取り込みスループットは、1秒あたり約4アイテムに調整されます。

* スキーマの更新はサポートされていません。 接続設定を作成した後、スキーマを更新する方法はありません。 接続を削除して再作成することはできません。

* インデックスが作成されたコンテンツは、カスタム縦の下にある検索結果ページにのみ表示されます。 この制限は、ユーザー設定の種類のコンテンツに適用されます。

* プレビュー期間中にセットアップした接続は、削除して再作成する必要がある場合があります。 これらの接続は、製品の改善に加えられた変更に互換性がない場合は機能しません。

* 接続制限があります。 各テナントは最大10個の接続を作成できます。

* ソースリポジトリのサイズ。 テスト済み検索スケールの制限である場合は、20万アイテムのソースリポジトリがあるコネクタをプレビューすることをお勧めします。 検索のパフォーマンスの向上に取り組んでいますが、近い将来、より大きなリポジトリサイズのサポートが期待されています。

* 接続の編集サポートを利用できません。 接続が作成されたら、編集または変更することはできません。 詳細を変更する必要がある場合は、接続を削除して再作成する必要があります。

* コネクタコンテンツは、カスタムの業種でのみ検索できます。

* コネクタのコンテンツは、1つの接続でのみ、各カスタム縦に表示でき、結果の種類の作成が必要になります。
