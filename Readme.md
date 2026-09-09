# KirtmunaMaven

KirtmunaによるModを配布するための、GitHubPagesで動作する静的Mavenリポジトリ

## リポジトリURL

```
https://kirtmuna.github.io/kirtmuna-maven/
```

## Gradleでの使い方

`build.gradle` の `repositories {}` に以下を追加してください。

```groovy
repositories {
    maven {
        name 'KirtmunaMaven'
        url 'https://kirtmuna.github.io/kirtmuna-maven/'
    }
}
```

必要なgroupのみに絞りたい場合は `content { includeGroup(...) }` を併記してください。

```groovy
maven {
    name 'KirtmunaMaven'
    url 'https://kirtmuna.github.io/kirtmuna-maven/'
    content { includeGroup 'jp.apple' }
}
```

Kotlin DSL (`build.gradle.kts`) の場合:

```kotlin
maven {
    name = "KirtmunaMaven"
    url = uri("https://kirtmuna.github.io/kirtmuna-maven/")
    content { includeGroup("jp.apple") }
}
```

依存関係の指定は通常のMavenとほぼ同じ。

```groovy
  implementation 'groupId:artifactId:version'
/** 例 **/
//implementation 'jp.apple:AppleExtended-forge1.12.2:2.5.2'
```

## 公開されているアーティファクト

| groupId | artifactId | 説明             |
|---|---|----------------|
| `jp.apple` | `AppleExtended-forge1.12.2` | AppleExtended  |

最新バージョンは各アーティファクトの `maven-metadata.xml` で確認できます。

```
https://kirtmuna.github.io/kirtmuna-maven/jp/apple/AppleExtended-forge1.12.2/maven-metadata.xml
```