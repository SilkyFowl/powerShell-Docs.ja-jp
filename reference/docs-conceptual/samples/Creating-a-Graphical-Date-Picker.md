---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: グラフィカルな日付の選択を作成する
description: この記事では、Windows PowerShell で .NET Framework のフォーム作成機能を使用して、カレンダー スタイルのカスタム コントロールを作成する方法を示します。
ms.openlocfilehash: b73c9ba78817af7c38c20642402752765a7a3674
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500506"
---
# <a name="creating-a-graphical-date-picker"></a>グラフィカルな日付の選択を作成する

ユーザーが日付を選択できる、グラフィカルな予定表スタイルのコントロールを備えたフォームを作成するには、Windows PowerShell 3.0 以降のリリースを使用します。

## <a name="create-a-graphical-date-picker-control"></a>グラフィカルな日付の選択コントロールの作成

以下を Windows PowerShell ISE にコピーしてから貼り付け、Windows PowerShell スクリプト (.ps1) として保存します。

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing

$form = New-Object Windows.Forms.Form -Property @{
    StartPosition = [Windows.Forms.FormStartPosition]::CenterScreen
    Size          = New-Object Drawing.Size 243, 230
    Text          = 'Select a Date'
    Topmost       = $true
}

$calendar = New-Object Windows.Forms.MonthCalendar -Property @{
    ShowTodayCircle   = $false
    MaxSelectionCount = 1
}
$form.Controls.Add($calendar)

$okButton = New-Object Windows.Forms.Button -Property @{
    Location     = New-Object Drawing.Point 38, 165
    Size         = New-Object Drawing.Size 75, 23
    Text         = 'OK'
    DialogResult = [Windows.Forms.DialogResult]::OK
}
$form.AcceptButton = $okButton
$form.Controls.Add($okButton)

$cancelButton = New-Object Windows.Forms.Button -Property @{
    Location     = New-Object Drawing.Point 113, 165
    Size         = New-Object Drawing.Size 75, 23
    Text         = 'Cancel'
    DialogResult = [Windows.Forms.DialogResult]::Cancel
}
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)

$result = $form.ShowDialog()

if ($result -eq [Windows.Forms.DialogResult]::OK) {
    $date = $calendar.SelectionStart
    Write-Host "Date selected: $($date.ToShortDateString())"
}
```

このスクリプトは 2 つの .NET Framework クラス、つまり **System.Drawing** と **System.Windows.Forms** を最初に読み込みます。 次に、.NET Framework クラス **Windows.Forms.Form** の新しいインスタンスを開始します。これにより、コントロールの追加を開始する空白のフォームまたはウィンドウが作成されます。

```powershell
$form = New-Object Windows.Forms.Form -Property @{
    StartPosition = [Windows.Forms.FormStartPosition]::CenterScreen
    Size          = New-Object Drawing.Size 243, 230
    Text          = 'Select a Date'
    Topmost       = $true
}
```

この例では、 **Property** プロパティとハッシュ テーブルを使って、このクラスの 4 つのプロパティに値を割り当てます。

1. **StartPosition** :このプロパティを追加しない場合は、Windows によりフォームが開かれる場所が選択されます。 このプロパティを **CenterScreen** に設定すると、フォームは読み込まれるたびに画面中央に自動的に表示されます。

2. **Size** :フォームのサイズをピクセル単位で表します。
   前述のスクリプトにより、幅 243 ピクセル、高さ 230 ピクセルのフォームが作成されます。

3. **Text** :ウィンドウのタイトルになります。

4. **Topmost** :このプロパティを `$true` に設定すると、開いているその他のウィンドウとダイアログ ボックスの最上部にウィンドウが強制的に開きます。

次に、作成し、フォームに [カレンダー] コントロールを追加します。
この例では、現在の日付は強調表示されておらず、丸で囲まれてもいません。
ユーザーは、予定表で 1 回に 1 日のみ選択できます。

```powershell
$calendar = New-Object Windows.Forms.MonthCalendar -Property @{
    ShowTodayCircle   = $false
    MaxSelectionCount = 1
}
$form.Controls.Add($calendar)
```

次に、フォームに **[OK]** ボタンを作成します。 **[OK]** ボタンのサイズと動作を指定します。 この例では、ボタンの位置は、フォームの上端から 165 ピクセル、左端から 38 ピクセルです。 ボタンの高さは 23 ピクセル、ボタンの幅は 75 ピクセルです。 スクリプトは、ボタンの動作を決定するために定義済みの Windows フォームの型を使用します。

```powershell
$okButton = New-Object Windows.Forms.Button -Property @{
    Location     = New-Object Drawing.Point 38, 165
    Size         = New-Object Drawing.Size 75, 23
    Text         = 'OK'
    DialogResult = [Windows.Forms.DialogResult]::OK
}
$form.AcceptButton = $okButton
$form.Controls.Add($okButton)
```

同様に、 **[キャンセル]** ボタンを作成します。
**[キャンセル]** ボタンの位置は、ウィンドウの最上部から 165 ピクセル、左端から 113 ピクセルです。

```powershell
$cancelButton = New-Object Windows.Forms.Button -Property @{
    Location     = New-Object Drawing.Point 113, 165
    Size         = New-Object Drawing.Size 75, 23
    Text         = 'Cancel'
    DialogResult = [Windows.Forms.DialogResult]::Cancel
}
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)
```

次のコード行を追加して、Windows でフォームを表示します。

```powershell
$result = $form.ShowDialog()
```

最後に、`if` ブロック内のコードにより、ユーザーがカレンダーで日付を選んでから、 **[OK]** ボタンをクリックするか **Enter** キーを押した後のフォームの操作を Windows に指示します。 Windows PowerShell は、ユーザーに選択された日付を表示します。

```powershell
if ($result -eq [Windows.Forms.DialogResult]::OK) {
    $date = $calendar.SelectionStart
    Write-Host "Date selected: $($date.ToShortDateString())"
}
```

## <a name="see-also"></a>参照

- [GitHub: Dave Wyatt の WinFormsExampleUpdates](https://github.com/dlwyatt/WinFormsExampleUpdates)
- [Windows PowerShell Tip of the Week: グラフィカルな日付の選択を作成する](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730942(v=technet.10))
