### <a name="allow-unicode-bidirectional-control-characters-in-uris"></a><span data-ttu-id="de757-101">URI での Unicode の双方向制御文字の許可</span><span class="sxs-lookup"><span data-stu-id="de757-101">Allow Unicode Bidirectional Control Characters in URIs</span></span>

|   |   |
|---|---|
|<span data-ttu-id="de757-102">説明</span><span class="sxs-lookup"><span data-stu-id="de757-102">Details</span></span>|<span data-ttu-id="de757-103">Unicode では、テキストの方向を指定するために使用される特殊な制御文字をいくつか指定します。</span><span class="sxs-lookup"><span data-stu-id="de757-103">Unicode specifies several special control characters used to specify the orientation of text.</span></span> <span data-ttu-id="de757-104">以前のバージョンの .NET Framework では、これらの文字は、パーセントでエンコードされたフォームに存在する場合でも、すべての URI から正しく削除されませんでした。</span><span class="sxs-lookup"><span data-stu-id="de757-104">In previous versions of the .NET Framework, these characters were incorrectly stripped from all URIs even if they were present in their percent-encoded form.</span></span> <span data-ttu-id="de757-105">[RFC 3987](http://tools.ietf.org/html/rfc3987) により適切に従うために、これらの文字を URI で使用できるようにしました。</span><span class="sxs-lookup"><span data-stu-id="de757-105">In order to better follow [RFC 3987](http://tools.ietf.org/html/rfc3987), we now allow these characters in URIs.</span></span> <span data-ttu-id="de757-106">これらの文字は、URI でエンコードされていないことがわかった場合、パーセントでエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="de757-106">When found unencoded in a URI, they are percent-encoded.</span></span> <span data-ttu-id="de757-107">パーセントでエンコードされていることがわかった場合は、そのままです。</span><span class="sxs-lookup"><span data-stu-id="de757-107">When found percent-encoded they are left as-is.</span></span>|
|<span data-ttu-id="de757-108">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="de757-108">Suggestion</span></span>|<span data-ttu-id="de757-109">4.7.2 以降のバージョンの .NET Framework を対象とするアプリケーションの場合は、Unicode の双方向文字のサポートが既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="de757-109">For applications that target versions of .NET Framework starting with 4.7.2, support for Unicode bidirectional characters is enabled by default.</span></span> <span data-ttu-id="de757-110">この変更が望ましくない場合、アプリケーションの構成ファイルの <code>&lt;runtime&gt;</code> セクションに次の [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) スイッチを追加することで無効にできます。</span><span class="sxs-lookup"><span data-stu-id="de757-110">If this change is undesirable, you can disable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the <code>&lt;runtime&gt;</code> section of the application configuration file:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre><span data-ttu-id="de757-111">以前のバージョンの .NET Framework を対象とするが、.NET Framework 4.7.2 以降のバージョンで実行するアプリケーションの場合、Unicode の双方向文字のサポートが既定で無効になります。</span><span class="sxs-lookup"><span data-stu-id="de757-111">For applications that target earlier versions of the .NET Framework but are running under versions starting with .NET Framework 4.7.2, support for Unicode bidirectional characters is disabled by default.</span></span> <span data-ttu-id="de757-112">アプリケーションの構成ファイルの <code>&lt;runtime&gt;</code> セクションに次の [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) スイッチを追加することで有効にできます。</span><span class="sxs-lookup"><span data-stu-id="de757-112">You can enable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the <code>&lt;runtime&gt;</code> section of the application configuration file::</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="de757-113">スコープ</span><span class="sxs-lookup"><span data-stu-id="de757-113">Scope</span></span>|<span data-ttu-id="de757-114">マイナー</span><span class="sxs-lookup"><span data-stu-id="de757-114">Minor</span></span>|
|<span data-ttu-id="de757-115">Version</span><span class="sxs-lookup"><span data-stu-id="de757-115">Version</span></span>|<span data-ttu-id="de757-116">4.7.2</span><span class="sxs-lookup"><span data-stu-id="de757-116">4.7.2</span></span>|
|<span data-ttu-id="de757-117">型</span><span class="sxs-lookup"><span data-stu-id="de757-117">Type</span></span>|<span data-ttu-id="de757-118">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="de757-118">Retargeting</span></span>|
|<span data-ttu-id="de757-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="de757-119">Affected APIs</span></span>|<ul><li><xref:System.Uri?displayProperty=nameWithType></li></ul>|
