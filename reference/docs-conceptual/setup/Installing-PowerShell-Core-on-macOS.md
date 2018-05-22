# <a name="installing-powershell-core-on-macos"></a><span data-ttu-id="bc176-101">macOS への PowerShell Core のインストール</span><span class="sxs-lookup"><span data-stu-id="bc176-101">Installing PowerShell Core on macOS</span></span>

<span data-ttu-id="bc176-102">PowerShell Core は、macOS 10.12 以降をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="bc176-102">PowerShell Core supports macOS 10.12 and higher.</span></span>
<span data-ttu-id="bc176-103">すべてのパッケージは GitHub [リリース][] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="bc176-103">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="bc176-104">パッケージがインストールされたら、ターミナルから `pwsh` を実行します。</span><span class="sxs-lookup"><span data-stu-id="bc176-104">Once the package is installed, run `pwsh` from a terminal.</span></span>

### <a name="installation-via-homebrew-on-macos-1012"></a><span data-ttu-id="bc176-105">Homebrew による macOS 10.12 へのインストール</span><span class="sxs-lookup"><span data-stu-id="bc176-105">Installation via Homebrew on macOS 10.12</span></span>

<span data-ttu-id="bc176-106">[Homebrew][brew] は、macOS 用の推奨されるパッケージ マネージャーです。</span><span class="sxs-lookup"><span data-stu-id="bc176-106">[Homebrew][brew] is the preferred package manager for macOS.</span></span>
<span data-ttu-id="bc176-107">`brew` コマンドが見つからない場合、[指示][brew]に従い、Homebrew をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc176-107">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

<span data-ttu-id="bc176-108">Homebrew をインストールすると、PowerShell のインストールが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="bc176-108">Once you've installed Homebrew, installing PowerShell is easy.</span></span>
<span data-ttu-id="bc176-109">最初に [Homebrew-Cask][cask] をインストールします。その後、たくさんのパッケージをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="bc176-109">First, install [Homebrew-Cask][cask], so you can install more packages:</span></span>

```sh
brew tap caskroom/cask
```

<span data-ttu-id="bc176-110">これで PowerShell をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="bc176-110">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell
```

<span data-ttu-id="bc176-111">最後に、インストールが正常に動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bc176-111">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="bc176-112">新しいバージョンの PowerShell がリリースされたら、Homebrew の式を更新し、PowerShell をアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="bc176-112">When new versions of PowerShell are released, simply update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="bc176-113">上記のコマンドは PowerShell (pwsh) ホストから呼び出すことができますが、その場合、PowerShell シェルを終了し、再起動して、アップグレードを完了し、</span><span class="sxs-lookup"><span data-stu-id="bc176-113">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="bc176-114">$PSVersionTable に表示される値を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc176-114">and refresh the values shown in $PSVersionTable.</span></span>

[brew]: http://brew.sh/
[cask]: https://caskroom.github.io/

### <a name="installation-via-direct-download"></a><span data-ttu-id="bc176-115">直接ダウンロードによるインストール</span><span class="sxs-lookup"><span data-stu-id="bc176-115">Installation via Direct Download</span></span>

<span data-ttu-id="bc176-116">[リリース][] ページから macOS マシンに PKG パッケージ `powershell-6.0.2-osx.10.12-x64.pkg` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="bc176-116">Download the PKG package `powershell-6.0.2-osx.10.12-x64.pkg` from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="bc176-117">ファイルをダブルクリックして画面の指示に従うか、ターミナルからインストールします。</span><span class="sxs-lookup"><span data-stu-id="bc176-117">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-6.0.2-osx.10.12-x64.pkg -target /
```

## <a name="binary-archives"></a><span data-ttu-id="bc176-118">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="bc176-118">Binary Archives</span></span>

<span data-ttu-id="bc176-119">macOS プラットフォームと Linux プラットフォームで高度な展開シナリオを実行するために、PowerShell バイナリ `tar.gz` アーカイブが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bc176-119">PowerShell binary `tar.gz` archives are provided for macOS and Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="bc176-120">macOS へのバイナリ アーカイブのインストール</span><span class="sxs-lookup"><span data-stu-id="bc176-120">Installing binary archives on macOS</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v6.0.2/powershell-6.0.2-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/6.0.2

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/6.0.2

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/6.0.2/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/6.0.2/pwsh /usr/local/bin/pwsh
```

## <a name="uninstalling-powershell-core"></a><span data-ttu-id="bc176-121">PowerShell Core のアンインストール</span><span class="sxs-lookup"><span data-stu-id="bc176-121">Uninstalling PowerShell Core</span></span>

<span data-ttu-id="bc176-122">Homebrew で PowerShell をインストールした場合、アンインストールが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="bc176-122">If you installed PowerShell with Homebrew, uninstallation is easy:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="bc176-123">直接ダウンロードで PowerShell をインストールした場合、手動で PowerShell を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc176-123">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="bc176-124">追加の PowerShell パスを削除するには、このドキュメントの「[パス][]」セクションを参照し、`sudo rm` を使用して目的のパスを削除してください。</span><span class="sxs-lookup"><span data-stu-id="bc176-124">To remove the additional PowerShell paths, please see the [paths][] section in this document and remove the desired the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="bc176-125">Homebrew でインストールした場合、この操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="bc176-125">This is not necessary if you installed with Homebrew.</span></span>

[パス]:#paths
[paths]:#paths

## <a name="paths"></a><span data-ttu-id="bc176-127">パス</span><span class="sxs-lookup"><span data-stu-id="bc176-127">Paths</span></span>

* <span data-ttu-id="bc176-128">`$PSHOME` は `/opt/microsoft/powershell/6.0.0/` です</span><span class="sxs-lookup"><span data-stu-id="bc176-128">`$PSHOME` is `/opt/microsoft/powershell/6.0.0/`</span></span>
* <span data-ttu-id="bc176-129">ユーザー プロファイルは `~/.config/powershell/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="bc176-129">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="bc176-130">既定のプロファイルは `$PSHOME/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="bc176-130">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="bc176-131">ユーザー モジュールは `~/.local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="bc176-131">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="bc176-132">共有モジュールは `/usr/local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="bc176-132">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="bc176-133">既定のモジュールは `$PSHOME/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="bc176-133">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="bc176-134">PSReadline 履歴は `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` に記録されます</span><span class="sxs-lookup"><span data-stu-id="bc176-134">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="bc176-135">プロファイルには、PowerShell のホスト単位の構成が考慮されています。</span><span class="sxs-lookup"><span data-stu-id="bc176-135">The profiles respect PowerShell's per-host configuration.</span></span>
<span data-ttu-id="bc176-136">そのため、既定のホスト固有のプロファイルは、同じ場所の `Microsoft.PowerShell_profile.ps1` に存在します。</span><span class="sxs-lookup"><span data-stu-id="bc176-136">So the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="bc176-137">PowerShell は、macOS の [XDG ベース ディレクトリ仕様][xdg-bds]を尊重しています。</span><span class="sxs-lookup"><span data-stu-id="bc176-137">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="bc176-138">macOS は BSD から派生しているので、プレフィックスに `/opt` ではなく `/usr/local` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="bc176-138">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span>
<span data-ttu-id="bc176-139">そのため、`$PSHOME` は `/usr/local/microsoft/powershell/6.0.0/` です。シンボリックリンクは `/usr/local/bin/pwsh` にあります。</span><span class="sxs-lookup"><span data-stu-id="bc176-139">Thus, `$PSHOME` is `/usr/local/microsoft/powershell/6.0.0/`, and the symlink is placed at `/usr/local/bin/pwsh`.</span></span>

[リリース]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html