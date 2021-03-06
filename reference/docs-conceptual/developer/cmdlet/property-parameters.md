---
title: プロパティパラメーター |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 0ded22dcda2b4eb957834ec092466767a4121f0e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781836"
---
# <a name="property-parameters"></a>プロパティのパラメーター

次の表に、プロパティパラメーターの推奨される名前と機能を示します。

|パラメーター|機能|
|---|---|
|**Count**<br>データ型: Int32|このパラメーターを実装して、処理するオブジェクトの数をユーザーが指定できるようにします。|
|**説明**<br>データ型: 文字列|ユーザーがリソースの説明を指定できるように、このパラメーターを実装します。|
|**From**<br>データ型: 文字列|ユーザーが情報を取得する参照オブジェクトを指定できるように、このパラメーターを実装します。|
|**Id**<br>データ型: リソースに依存|ユーザーがリソースの識別子を指定できるように、このパラメーターを実装します。|
|**入力**<br>データ型: 文字列|ユーザーが入力ファイルの仕様を指定できるように、このパラメーターを実装します。|
|**場所**<br>データ型: 文字列|ユーザーがリソースの場所を指定できるように、このパラメーターを実装します。|
|**LogName**<br>データ型: 文字列|処理または使用するログファイルの名前をユーザーが指定できるように、このパラメーターを実装します。|
|**Name**<br>データ型: 文字列|ユーザーがリソースの名前を指定できるように、このパラメーターを実装します。|
|**出力**<br>データ型: 文字列|ユーザーが出力ファイルを指定できるように、このパラメーターを実装します。|
|**所有者**<br>データ型: 文字列|ユーザーがリソースの所有者の名前を指定できるように、このパラメーターを実装します。|
|**Property**<br>データ型: 文字列|ユーザーが使用するプロパティ名または名前を指定できるように、このパラメーターを実装します。|
|**理由**<br>データ型: 文字列|このパラメーターを実装して、このコマンドレットが呼び出される理由をユーザーが指定できるようにします。|
|**Regex**<br>データ型: SwitchParameter|パラメーターを指定したときに正規表現が使用されるように、このパラメーターを実装します。 このパラメーターを指定すると、ワイルドカード文字は解決されません。|
|**速度**<br>データ型: Int32|ユーザーがボーレートを指定できるように、このパラメーターを実装します。 ユーザーは、このパラメーターをリソースの速度に設定します。|
|**State**<br>データ型: キーワード配列|ユーザーが状態の名前 (KEYDOWN など) を指定できるように、このパラメーターを実装します。|
|**Value**<br>データ型: オブジェクト|コマンドレットに渡す値をユーザーが指定できるように、このパラメーターを実装します。|
|**[バージョン]**<br>データ型: 文字列|ユーザーがプロパティのバージョンを指定できるように、このパラメーターを実装します。|

## <a name="see-also"></a>参照

[コマンドレットのパラメーター](./cmdlet-parameters.md)

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
