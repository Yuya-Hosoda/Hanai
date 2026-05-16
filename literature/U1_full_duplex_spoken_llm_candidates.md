# U1 候補文献リスト
## リアルタイム音声 LLM／全二重音声アーキテクチャ／Moshi 系パラダイム

**状態:** 候補文献の整理段階。本文用のレビュー文章はまだ作成していない。
**目的:** Moshi／MoshiRAG が導入する設計要素と、ストリーミング音声言語モデルの研究状況を把握する。
**作成日:** 2026-05-16
**段階:** Step 4（検索）完了、Step 5（抽出）は未実施。
**ガバナンス:** 論文で使う主張は、出典存在確認（L1）、書誌情報確認（L2）、主張と出典の対応確認（L3）を済ませてから採用する。

---

## 1. 調査範囲

検索語は、Moshi、full-duplex spoken dialogue、real-time voice language model、streaming speech LLM、inner monologue token、Mimi codec、RQ-Transformer、streaming ASR、simultaneous speech、voice-to-voice model、SpeechLM、AudioLM、MoshiRAG、retrieval augmented spoken dialogue などを中心に設定した。検索対象は arXiv、ACL Anthology、IEEE Xplore/TASLP、NeurIPS 2024、AAAI 2025、Semantic Scholar、OpenReview である。

---

## 2. 候補文献の概要

候補は 17 件である。査読済みとして確認できたものは AudioLM、dGSLM、LSLM、NeurIPS 2024 の全二重対話方式、WavRAG の 5 件である。Moshi、MoshiRAG、各種ベンチマークやサーベイは重要だが、多くは arXiv プレプリントであり、本文では「確立済み研究」ではなく「アーキテクチャ上の参考文献」または「最新動向」として扱う。

主要候補は次の通り。

| ID | 文献 | 位置づけ |
|---|---|---|
| C01 | Moshi: a speech-text foundation model for real-time dialogue | MoshiRAG の前提となる中核的アーキテクチャ。査読状況は未確認のため arXiv と明記する。 |
| C02 | MoshiRAG: Asynchronous Knowledge Retrieval for Full-Duplex Speech Language Models | 本研究の発想に最も近いが、2026 年時点で査読中。重要なマテリアルギャップとして管理する。 |
| C03 | AudioLM | 音声を階層的な離散コードとして扱う代表的研究。 |
| C04 | dGSLM | 音声対話を生成的言語モデリングとして扱う先行研究。 |
| C05 | Language Model Can Listen While Speaking | 「話しながら聞く」全二重音声モデルの重要文献。 |
| C06 | Full-duplex Speech Dialogue Scheme Based on LLMs | LLM ベースの全二重音声対話方式。 |
| C07 | WavRAG | 音声対話モデルに RAG を組み込む研究で、U1 と U2 の両方に関係する。 |

---

## 3. 採用判断

### 採用（7 件）
Moshi、MoshiRAG、AudioLM、dGSLM、LSLM、NeurIPS 2024 の全二重対話方式、WavRAG を中心的に扱う。理由は、本研究の「全二重音声対話」「音声トークン化」「同時入出力」「RAG との接続」に直接関係するためである。

### 保留（6 件）
全二重音声モデルのサーベイ、Spoken Language Model サーベイ、Full-Duplex-Bench 系、Mini-Omni などは、背景説明や評価動向の補助資料として有用だが、査読状況や著者情報の確認が必要である。

### U1 から除外（4 件）
X-Talk、LLM-enhanced dialogue management、SALM-Duplex、日本語全二重対話システムなどは、近接領域として記録するが、U1 の中核論拠にはしない。

---

## 4. マテリアルギャップ

**U1-MoshiRAG:** MoshiRAG は本研究の設計に強く関係するが、査読済み文献として確定していない。したがって、論文では「確立された先行研究」としてではなく、「参考アーキテクチャ」「最新プレプリント」として限定的に使う。

---

## 5. 次の作業

採用文献から、全二重性、遅延、音声トークン化、Inner Monologue、RAG 接続、ターンテイキング評価に関する主張を抽出し、Claim-Citation Matrix に L3 レベルで登録する。
