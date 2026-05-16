# U2 候補文献リスト
## RAG アーキテクチャ：非同期型・ストリーミング型

**状態:** 候補文献リスト。レビュー本文は未作成。
**研究上の問い:** RAG をリアルタイム対話に組み込む際、検索をどのタイミングで実行し、生成との遅延競合をどう抑えるか。
**作成日:** 2026-05-16
**ガバナンス:** RAG の効果や遅延改善を主張する場合は、必ず出典との対応を確認する。

---

## 1. 調査範囲

検索語は retrieval-augmented generation、streaming RAG、asynchronous RAG、real-time RAG、adaptive retrieval、FLARE、Self-RAG、modular RAG、audio RAG、spoken dialogue RAG、MoshiRAG、WavRAG などである。arXiv、ACL Anthology、IEEE、NeurIPS、ICLR、OpenReview、Semantic Scholar を調査した。

---

## 2. 候補文献の概要

RAG の基礎として Lewis et al. の Retrieval-Augmented Generation、構成分類として Naive/Advanced/Modular RAG サーベイ、検索タイミングを制御する FLARE と Self-RAG、並列検索を扱う Stream RAG、音声対話寄りの WavRAG と MoshiRAG を重視する。

| 区分 | 主な文献 | 本研究での使い方 |
|---|---|---|
| RAG の基礎 | Retrieval-Augmented Generation | パラメトリック記憶と非パラメトリック記憶を併用する考え方の根拠。 |
| RAG の分類 | Modular RAG Survey | RAG をモジュール化して説明する枠組み。 |
| 適応的検索 | FLARE, Self-RAG | 必要な時だけ検索する設計の参考。 |
| ストリーミング／低遅延 | Stream RAG | 生成と検索を並列化し、遅延を抑える考え方の参考。 |
| 音声対話 RAG | WavRAG, MoshiRAG | 音声対話に RAG を組み込む最新動向。ただし MoshiRAG は査読状況に注意。 |

---

## 3. 採用判断

### 採用（6 件）
RAG の基礎論文、RAG サーベイ、FLARE、Self-RAG、Stream RAG、WavRAG を採用する。これらは、検索の必要性、検索タイミング、モジュール化、ストリーミング生成との接続を説明するために使える。

### 保留（4 件）
MoshiRAG や関連プレプリントは本研究に近いが、査読状況が未確定であるため、設計参考として限定的に扱う。

### U2 から除外または再分類（2 件）
音声モデルやロボット対話に主眼があり、RAG アーキテクチャの根拠としては弱いものは、U1、U7、U8 へ回す。

---

## 4. マテリアルギャップ

リアルタイムの全二重音声対話で、ユーザへの応答開始を遅らせずにドメイン知識検索を行い、音声応答の情報提示部分に間に合わせる、という設計を査読済み文献だけで完全に支えることはまだ難しい。このギャップが、本研究の非同期 RAG 統合の新規性につながる。

---

## 5. 次の作業

採用文献から、検索トリガ、検索と生成の並列化、遅延評価、検索失敗時のフォールバック、RAG のモジュール構成に関する主張を抽出する。
