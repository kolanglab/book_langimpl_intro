# さらに学ぶために

本書は言語処理系の「入り口」を一通り歩く入門書でした。各テーマには、それぞれ一冊分の奥行きがあります。ここでは、本文中で紹介した姉妹編と、定番の教科書をまとめます。次の一歩の道しるべにしてください。

## 姉妹編（kolanglab シリーズ）

本書で「詳細は別テキスト」とした各テーマは、以下の姉妹編で深く扱っています。

**前提・補助**

- 『[言語処理系を作りたい人のためのC言語入門](https://kolanglab.github.io/book_clang_intro/)』── 処理系を書くために必要な C を、目的から逆算して学ぶ。

**フロントエンド（解析）**

- 『[構文解析入門](https://kolanglab.github.io/book_parser_intro)』── 字句解析・構文解析の理論と実装。LL/LR/PEG といった解析手法やパーサジェネレータの使い方。本書「構文解析」章の先へ。
- 『[言語処理系の意味解析入門](https://kolanglab.github.io/book_semantic_intro/#cover)』── 名前解決、型検査・型推論、データフロー解析、抽象解釈。本書「意味解析」章の先へ。

**データ構造と表現**

- 『[言語処理系のデータ構造入門](https://kolanglab.github.io/book_data_design/)』── シンボルテーブル・AST・値表現など処理系内部のデータ構造から、文字列・配列・ハッシュなど言語が提供するデータ型の実装まで。

**メモリ管理**

- 『[malloc 入門](https://kolanglab.github.io/book_malloc/)』── C の malloc/free の裏側を、API と OS インターフェースから、フリーリスト・バディ・スラブなどの基本アルゴリズム、dlmalloc / jemalloc / TCMalloc / mimalloc といった実際のライブラリの設計まで一望する。
- 『[保守的 GC 入門](https://kolanglab.github.io/book_Conservative_GC/)』── ポインタを正確に把握せずに動く保守的 GC の仕組みと実装。
- 『[正確な GC 入門](https://kolanglab.github.io/book_precise_gc/)』── 値の型情報を使う正確な GC の仕組みと実装。
- 『[GC の詳細](https://kolanglab.github.io/book_gc_details/)』── 世代別・インクリメンタル・並行 GC など、進んだ GC の話題。

**ランタイムとバックエンド**

- 『[言語処理系と I/O](https://kolanglab.github.io/book_lang_io/#cover)』── 入出力の仕組み、システムコール、ブロッキング／非同期 I/O。本書「入出力と処理系の拡張」章の先へ。
- 『[並行・並列言語処理系](https://kolanglab.github.io/book_parallel_lang/#cover)』── スレッド・コルーチン・並列実行を処理系がどう支えるか。本書「並行制御」章の先へ。
- 『[コード生成入門](https://kolanglab.github.io/book_code_gen/#cover)』── 機械語生成、レジスタ割り当て、命令選択。本書「JIT・AOT コンパイルと部分評価」章の先へ。
- 『[JITコンパイル入門](https://kolanglab.github.io/book_jit_intro/)』── トレーシング・メタトレーシング・階層的 JIT・脱最適化といった技法から、最新研究・各処理系のケーススタディまで。本書「JIT・AOT コンパイルと部分評価」章のさらに先へ。
- 『[ELF/DWARF 入門](https://kolanglab.github.io/book_elf_dwarf/)』── 実行ファイル形式 ELF とデバッグ情報形式 DWARF を、ヘッダ・セクション・シンボルから仕様の深部まで踏み込み、自作ツールのハンズオンも交えて解説。
- 『[デバッガ開発入門](https://kolanglab.github.io/book_debugger_intro/)』── ブレークポイント・ステップ実行・状態検査など、デバッガの仕組みと作り方。

## 定番の教科書・書籍

言語処理系をさらに体系的に学ぶための、世界的に定評のある書籍です。

- アホ・ラム・セシ・ウルマン『Compilers: Principles, Techniques, and Tools（第2版）』── 通称「ドラゴンブック」。コンパイラ理論の最も有名な教科書[Aho et al., 2006](#cite:aho2006)。
- クーパー・トーザン『Engineering a Compiler（第2版）』── 実装寄りの視点でコンパイラ全体を扱う、読みやすい定番[Cooper and Torczon, 2011](#cite:cooper2011)。
- アペル『Modern Compiler Implementation in ML』── 関数型言語でコンパイラを作りながら学ぶ構成[Appel, 1998](#cite:appel1998)。
- マクニック『Advanced Compiler Design and Implementation』── 最適化に重点を置いた、より進んだ一冊[Muchnick, 1997](#cite:muchnick1997)。
- ニストロム『Crafting Interpreters』── インタプリタを 2 つ（木をたどる版とバイトコード版）作りながら学ぶ実践書。Web 版は無料公開されており、本書と問題意識が最も近い[Nystrom, 2021](#cite:nystrom2021)。
- ピアス『Types and Programming Languages』── 型システムの理論を本格的に学ぶ定番[Pierce, 2002](#cite:pierce2002)。
- ジョーンズ・ホスキング・モス『The Garbage Collection Handbook』── GC のあらゆる方式を網羅した決定版[Jones et al., 2012](#cite:jones2012)。

## 古典論文

本書で触れた、分野の礎となった論文です。原典にあたると、アイデアが生まれた瞬間の鮮度に触れられます。

- マッカーシー（1960）── LISP と GC の出発点[McCarthy, 1960](#cite:mccarthy1960)。
- ベル（1973）── スレッデッドコード[Bell, 1973](#cite:bell1973)。
- スティール（1977）── 末尾呼び出しと「LAMBDA: The Ultimate GOTO」[Steele, 1977](#cite:steele1977)。
- ドイチュ・シフマン（1984）── インラインキャッシュの誕生[Deutsch and Schiffman, 1984](#cite:deutsch1984)。
- ヘルツェ・チェンバース・アンガー（1991）── 多態インラインキャッシュ[Hölzle et al., 1991](#cite:holzle1991)。
- フタムラ（1971）── 部分評価と Futamura 投影[Futamura, 1971](#cite:futamura1971)。
- エイコック（2003）── JIT コンパイルの歴史を概観[Aycock, 2003](#cite:aycock2003)。

> [!TIP]
> 何よりの学習法は「**作ってみること**」です。本書の MiniRuby を拡張する、好きな言語の小さなインタプリタを書く、自分だけの DSL を設計する ── どんな小さな処理系でも、自分で動かした経験は、何冊の本にも勝る理解をもたらします。あなたの作る言語が、この世界の次の一歩になりますように。
