### <a name="building-an-entity-framework-edmx-with-visual-studio-2013-can-fail-with-error-msb4062-if-using-the-entitydeploysplit-or-entityclean-tasks"></a>Visual Studio 2013 で Entity Framework edmx をビルドすると、EntityDeploySplit または EntityClean タスクを使用している場合、エラー MSB4062 で失敗することがある

|   |   |
|---|---|
|詳細|MSBuild 12.0 ツール (Visual Studio 2013 に含まれる) は、MSBuild ファイルの位置を変更したため、古い Entity Framework のターゲット ファイルは無効になります。 その結果、<code>EntityDeploySplit</code> および <code>EntityClean</code> タスクは、<code>Microsoft.Data.Entity.Build.Tasks.dll</code> を見つけられないために失敗します。 このエラーは、ツールセット (MSBuild/VS) の変更によるものであり、.NET Framework の変更によるものではないことに注意してください。 開発者ツールをアップグレードしたときにのみ発生し、.NET Framework をアップグレード下だけでは発生しません。|
|提案される解決策|Entity Framework のターゲット ファイルは、.NET Framework 4.6 以降の新しい MSBuild レイアウトで機能するように修正されます。 このバージョンの Framework にアップグレードすることで、この問題は修正されます。 または、[この](http://stackoverflow.com/a/24249247/131944) 回避策を使用して、ターゲット ファイルに直接パッチを当てることができます。|
|スコープ|Major|
|Version|4.5.1|
|型|再ターゲット中|

