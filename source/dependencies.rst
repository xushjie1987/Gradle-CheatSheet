依存関係の管理
=========================

.. sourcecode:: groovy

   dependencies {
     compile 'org.springframework:spring-core:2.5'
     // アーティファクトオンリー記法
     compile 'org.gradle.test.classifiers:service:1.0:jdk15@jar'
     // 推移的な依存関係の除外
     compile 'org.hibernate:hibernate:3.0.5') {
        transitive = true
     }

     // ローカルのファイル依存関係
     compile fileTree(dir: 'libs', include: '*.jar')
   }

依存関係のキャッシュ
~~~~~~~~~~~~~~~~~~~~~~~~~

dependencies に記述した依存するサードパーティのアーティファクト（依存モジュール）は
以下の優先順位でキャッシュされる。

1. ${GRADLE_USER_HOME}/cache
2. ${USER_HOME}/.gradle/cache

Mavenキャッシュと管理方法が異なるので、そのまま Maven リポジトリとして公開はできない、
