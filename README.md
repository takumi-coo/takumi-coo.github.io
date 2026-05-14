#研究について

## 楽曲間時系列類似度マップによる音楽理解支援

### 概要

私は，複数楽曲間の時間的な類似性を可視化し，ユーザの音楽理解を支援するシステムの研究を行っています．:contentReference[oaicite:0]{index=0}

人は「この曲とあの曲は似ている」と感じることがありますが，その類似性が楽曲中のどの時間区間に由来しているのか，また，どのような音楽的特徴によって生じているのかを説明することは容易ではありません．:contentReference[oaicite:1]{index=1}

本研究では，楽曲間の類似性を単に数値として提示するのではなく，ユーザ自身が類似区間を視覚的・聴覚的に確認しながら探索的に理解できる枠組みを提案しています．:contentReference[oaicite:2]{index=2}

具体的には，対照学習によって学習した時系列埋め込み表現を用いて二楽曲間の類似度を計算し，それを「時系列類似度マップ」として可視化します．ユーザは類似度マップ上で領域を選択し，対応する音源区間を実際に聴取することで，楽曲間に共通する音楽的特徴を直感的に理解できます．:contentReference[oaicite:3]{index=3}

---

### 研究背景

従来の音楽類似度推定では，楽曲全体を対象とした類似度計算が主流であり，「どの時間区間同士が似ているのか」を理解することは困難でした．:contentReference[oaicite:4]{index=4}

また，音楽理解は単なる情報提示ではなく，「聴く」「比較する」「操作する」といった能動的な行為を通じて形成される側面があります．:contentReference[oaicite:5]{index=5}

本研究では，ユーザ自身が類似性を探索し，実際に音源を聴取しながら理解を深めることを重視しています．

---

### 提案システム

本システムは以下の流れで構成されています．:contentReference[oaicite:6]{index=6}

1. 音源から音響特徴量を抽出
2. 深層学習モデルによって時系列埋め込みを生成
3. 楽曲間フレーム類似度を計算
4. 類似度マップとして可視化
5. ユーザが類似区間を選択・比較再生

類似度マップでは，

- 横軸：楽曲Bの時間
- 縦軸：楽曲Aの時間

として表示し，高類似度領域を色の明るさによって表現します．:contentReference[oaicite:7]{index=7}

---

### 使用技術

#### 音楽情報処理

- librosa
- Chroma Feature
- Mel Spectrogram
- Demucs
- torchcrepe
- pyworld

#### 深層学習

- PyTorch
- Contrastive Learning
- InfoNCE Loss
- LSTM Encoder

#### 可視化・UI

- pygame
- matplotlib

---

### 技術的特徴

#### 時系列埋め込み学習

楽曲を 250ms ごとのフレームへ分割し，各フレームから音響特徴量を抽出します．:contentReference[oaicite:8]{index=8}

その後，LSTM を用いて時間的文脈を考慮した埋め込みベクトルへ変換します．:contentReference[oaicite:9]{index=9}

#### 対照学習

同一楽曲内の連続フレームを正例，他楽曲フレームを負例として InfoNCE Loss により学習を行います．:contentReference[oaicite:10]{index=10}

これにより，

- 時間的に近い音楽特徴
- 楽曲固有の特徴
- 楽曲間の類似構造

を反映した埋め込み空間を獲得します．

#### 類似度マップ

学習済み埋め込み系列間のコサイン類似度を計算し，時系列類似度マップを生成します．:contentReference[oaicite:11]{index=11}

ユーザはマップ上で矩形領域を選択し，対応区間を比較再生できます．:contentReference[oaicite:12]{index=12}

---

### 現在の研究内容

現在は以下のテーマに取り組んでいます．

- 楽曲間の時間的類似性学習
- J-POP におけるサビ区間の表現学習
- 楽曲構造を考慮した類似性分析
- インタラクティブな音楽理解支援
- 音楽的特徴の可視化
- 類似区間の探索インタフェース設計

---

### 今後の展望

今後は，

- 人間の知覚印象を考慮した学習
- メロディ・コード・リズムごとの類似性分析
- 音楽理論に基づく説明生成
- 大規模言語モデルを用いた類似性説明

などを取り入れ，「なぜ似ているのか」をより説明可能な形で提示できる音楽理解支援システムへの発展を目指しています．:contentReference[oaicite:13]{index=13}

---

### Research Keywords

- Music Information Retrieval (MIR)
- Deep Learning
- Contrastive Learning
- Music Similarity
- Interactive Systems
- Music Understanding Support
- Visualization

---

### Author

Takumi Okada
