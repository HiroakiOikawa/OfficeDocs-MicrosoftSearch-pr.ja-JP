---
title: Microsoft Search 用 Azure Data Lake connector
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
description: Microsoft Search 用の Azure Data Lake Storage Gen2 connector をセットアップする
ms.openlocfilehash: 392960a5f7e6c93442ac7e1f60245217e194b42b
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626473"
---
# <a name="azure-data-lake-storage-gen2-connector-for-microsoft-search"></a>Microsoft Search 用 Azure Data Lake Storage Gen2 connector

[Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)コネクタを使用すると、組織内のユーザーはファイルとそのコンテンツを検索できます。 このコネクタは、azure Data Lake Storage Gen 2 アカウント内の Azure Blob コンテナーおよび階層対応フォルダーに格納されているデータにアクセスします。

この記事は、 [Microsoft 365](https://www.microsoft.com/microsoft-365)管理者または Azure Data Lake Storage Gen2 connector を構成、実行、および監視するユーザーを対象としています。 コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。

## <a name="connect-to-a-data-source"></a>データソースへの接続

### <a name="primary-storage-connection-string"></a>プライマリストレージ接続文字列 
[**認証と構成**] 画面で、プライマリストレージ接続文字列を指定します。 この文字列は、ストレージアカウントへのアクセスを許可するために必要です。 接続文字列を検索するには、 [azure portal](https://ms.portal.azure.com/#home)に移動して、 [Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)アカウントの [**キー** ] セクションに移動します。 接続文字列をコピーして画面の適切なフィールドに貼り付けます。

**AccountKey** (プライマリストレージ接続文字列のパラメーター) を指定しない場合は、Graph connector Service への読み取りアクセス権を与える必要があります。 Azure Data Lake Storage Gen2 アカウントの [**アクセス制御**] タブで、そのページの指示に従って、次のアプリへのアクセス権を付与します。
* **最初のパーティのアプリ ID:** 56c1da01-2127648f7-9355-af6d59d2766
* **ファーストパーティのアプリ名:** Graph Connector サービス

### <a name="storage-account-and-queue-notifications-optional"></a>ストレージアカウントとキューの通知 (オプション)
グラフコネクタサービスでリアルタイムでの変更の処理のサポートが今後追加される可能性があります。 その場合は、 [Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)の変更通知をキューに格納します。 Azure Data Lake Storage Gen2 と同じアカウント、または別のストレージアカウントにキューを作成する必要があります。

キューを作成した後、[キュー] ページの [**イベント**] タブに移動して、**イベントサブスクリプション**を構成します。 キューが受信するすべての Blob イベントを選択し、そのキューを Azure Data Lake Storage Gen2 アカウントに接続します。

## <a name="manage-the-search-schema"></a>検索スキーマを管理する
[**スキーマの管理**] 画面には、管理プロパティに関連付けられているスキーマ属性 (**クエリ**可能、**検索**可能、および取得**可能) を**変更するオプションがあります。 これらの管理プロパティの属性は、 [Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)アカウントからインデックスが作成されたデータです。

## <a name="manage-search-permissions"></a>検索アクセス許可を管理する
[**検索権限の管理**] 画面では、ストレージアカウントからアクセス制御リスト (acl) を取り込みます。 これらの検索権限が設定されている場合、コンテンツを検索するサインインしている[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/)ユーザーに割り当てられているアクセス許可に基づいて、検索コンテンツがトリミングされます。 または、組織内のすべてのユーザーに対して、ストレージアカウントからインデックスが作成されたすべてのコンテンツを表示するように選択することもできます。 この場合、組織内のすべてのユーザーがストレージアカウントのすべてのデータにアクセスできます。
 
## <a name="set-the-refresh-schedule"></a>更新スケジュールを設定する
[**更新の設定**] 画面で、増分クロールの間隔とフルクロールの間隔を設定できます。 [Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)コネクタの既定の間隔は、増分クロールの場合は15分、フルクロールの場合は1週間です。
 
## <a name="limitations"></a>制限事項
現時点では、 [Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)マルチプロトコルアクセスを使用できるのは、中部標準時、西中央アメリカ、カナダ中部、東部アメリカ、東アジア、北ヨーロッパ、東 US2、南アジア、西ヨーロッパ、西ヨーロッパ、西 US2、およびブラジル南部のみです。

更新プログラムと詳細については、「 [Azure Data Lake Storage でのマルチプロトコルアクセス (プレビュー)](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-multi-protocol-access)」を参照してください。


