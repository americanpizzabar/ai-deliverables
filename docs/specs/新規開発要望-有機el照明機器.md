## (1) 要件定義書

---
title: 有機EL照明機器 新規開発プロジェクト要件定義書
date: 2023-10-27
author: Leo (ECUANEST合同会社 新規事業開発部AI)
status: Draft
version: 1.0.0
tags: [有機EL照明, 新規開発, 要件定義, プロダクト企画, B2B, デザイン照明, スマート照明]
related_docs: [有機EL照明機器 新規開発要望に関するマーケティング調査書]
---

### 1. 導入

本要件定義書は、ECUANEST合同会社 調査・マーケティング部AI「Mia」による「有機EL照明機器 新規開発要望に関するマーケティング調査書」を踏まえ、新規事業開発部AI「Leo」が有機EL照明機器のプロトタイプ開発に向けたサービス企画および要件定義を行うものである。本製品は、有機EL照明の持つ独自の特性を最大限に活かし、特定の高付加価値市場における顧客ニーズに応えることを目的とする。

### 2. プロダクト概要

#### 2.1. プロダクト名（仮称）

ECUANEST LuminaFlex OLED Solution

#### 2.2. プロダクトビジョン

有機EL照明の「薄型・面発光・高演色性・目に優しい光」という独自の価値を最大限に引き出し、従来の照明では実現できなかった「唯一無二の空間体験」と「ブランドイメージを象徴するデザイン」を提供する、次世代のデザイン照明ソリューション。

#### 2.3. ターゲット市場と顧客

B2B市場を主軸とし、特に以下のペルソナを主要ターゲットとする。

*   **高級ホテル/商業施設の内装デザイナー:**
    *   **課題:** 既存照明では困難な、独創的で高級感のある空間演出。省エネ、メンテナンス性、環境配慮も要求。
    *   **ニーズ:** 自由な形状、空間に溶け込むデザイン、目に優しい上質な光質、シーンに応じた調光・調色機能、長期的な運用コスト抑制、環境負荷の低いソリューション。
*   **美術館・博物館のキュレーター/設計担当者:**
    *   **課題:** 展示物の色彩を忠実に再現し、劣化リスクを最小限に抑える照明。
    *   **ニーズ:** 高演色性、低発熱、紫外線・ブルーライトの低減、柔軟な配光制御。

#### 2.4. プロダクトコンセプト

1.  **デザインと統合:** 薄型・フレキシブルな特性を活かし、建築空間や家具にシームレスに統合されるデザイン。
2.  **上質な光体験:** 高演色性かつ均一な面発光による、目に優しく、対象物の魅力を最大限に引き出す光質。ブルーライト低減。
3.  **スマートな光制御:** 色温度（暖色〜寒色）、明るさ（調光）を自在に調整可能。シーンプリセット機能や外部システム（スマートホーム、ビル管理システム）との連携。
4.  **サステナビリティ:** 水銀フリー、低発熱、長寿命化による環境負荷低減と運用コスト削減。

### 3. 機能要件

#### 3.1. 照明パネル本体

*   **形状:** 薄型、フレキシブルまたは曲面対応の有機ELパネル。
*   **発光方式:** 均一な面発光。
*   **光質:**
    *   高演色性（Ra90以上を目標）。
    *   ブルーライト低減。
    *   フリッカーフリー。
*   **サイズ:** 複数サイズ展開（例: 10x10cm、10x30cm、30x30cmなど）。カスタマイズ対応オプション。
*   **寿命:** 20,000時間以上（初期輝度50%まで）を目標。
*   **発熱:** 低発熱設計。

#### 3.2. 制御システム

*   **ON/OFF制御:** 照明の点灯・消灯。
*   **調光機能:** 明るさを0%から100%まで無段階で調整可能。
*   **調色機能:** 色温度を2700K（暖色）から6500K（寒色）まで調整可能。
*   **シーンプリセット:** 複数の調光・調色設定を登録・呼び出し可能（例: 「リラックス」「集中」「展示モード」など）。
*   **グループ制御:** 複数の照明パネルをグループ化し、一括で制御可能。
*   **スケジュール機能:** 特定の時間に自動でON/OFF、調光・調色設定を変更。

#### 3.3. ユーザーインターフェース (UI)

*   **Webアプリケーション:** PC、タブレット、スマートフォンからアクセス可能な管理画面。
    *   直感的なダッシュボードで、各照明パネルまたはグループの状態を一覧表示。
    *   スライダー、カラーピッカー等を用いた調光・調色設定。
    *   シーンプリセットの作成・編集・適用。
    *   スケジュール設定。
*   **API提供:** 外部システム（スマートビルディングシステム、IoTプラットフォーム）との連携を可能にするRESTful APIまたはWebSocket API。
    *   照明の状態取得、制御コマンド送信。
    *   認証・認可メカニズム。

### 4. 非機能要件

#### 4.1. 性能要件

*   **応答速度:** UIからの操作後、照明が0.5秒以内に反応すること。
*   **輝度:** 最大輝度1,000cd/m²以上（プロトタイプではシミュレーション）。
*   **消費電力:** 高効率設計により、同等輝度のLED照明と比較して競争力のある消費電力を目指す。

#### 4.2. 信頼性要件

*   **安定稼働:** 24時間365日の連続稼働に耐えうる設計。
*   **故障率:** 年間故障率0.5%以下を目標。
*   **保証期間:** 製品本体5年間、制御システム2年間を基本とする。

#### 4.3. 保守性要件

*   **モジュール設計:** パネル、電源、制御ユニットが独立したモジュール設計で、部品交換やアップグレードが容易であること。
*   **リモート診断:** 制御システムにリモート診断機能を実装し、故障検知や状態監視が可能であること。

#### 4.4. 拡張性要件

*   **デバイス追加:** 将来的に新たな有機ELパネルの種類やサイズ、センサー連携機能などを容易に追加できるアーキテクチャ。
*   **システム連携:** 標準的なプロトコル（DALI, Zigbee, Matterなど）への対応を将来的に検討。

#### 4.5. セキュリティ要件

*   **アクセス制御:** ユーザー認証（ID/パスワード）と権限管理。
*   **通信暗号化:** API通信はHTTPS/WSSによる暗号化を必須とする。
*   **ファームウェア更新:** セキュアなファームウェア更新メカニズム。

#### 4.6. 運用要件

*   **設置・施工:** 薄型・軽量を活かし、設置作業が容易であること。
*   **電源:** AC100V-240V対応。
*   **環境:** 動作温度範囲 0℃〜40℃、湿度 20%〜80% (結露なきこと)。

#### 4.7. 環境要件

*   **RoHS指令:** 準拠。
*   **水銀フリー:** 有機ELの特性を活かし、水銀を含まない。
*   **リサイクル性:** 部材のリサイクル性を考慮した設計。

#### 4.8. コスト要件

*   **目標価格帯:** 同等性能の高級LEDデザイン照明と比較して、高付加価値を考慮した競争力のある価格設定。
*   **運用コスト:** 長寿命化と省エネにより、長期的なTCO（総所有コスト）を低減。

#### 4.9. 法規制要件

*   **電気用品安全法（PSEマーク）:** 準拠。
*   **電波法:** 無線通信機能を持つ場合、技術基準適合証明（技適マーク）を取得。
*   **CEマーキング、UL認証:** 将来的な海外展開を視野に入れ、対応を検討。

### 5. スコープ外の機能（現時点）

*   **人感センサー・照度センサーとの連携による自動制御:** 将来的な拡張機能として検討。
*   **音声アシスタント連携:** 将来的な拡張機能として検討。
*   **モバイルアプリ単体での提供:** Webアプリを優先し、必要に応じて検討。
*   **大規模なビル管理システムとの直接連携（複雑なBMSプロトコル）:** API連携を主とし、複雑なプロトコルへの直接対応は将来的に検討。

### 6. 開発フェーズとマイルストーン

1.  **フェーズ1: プロトタイプ開発 (PoC)**
    *   期間: 2ヶ月
    *   目標: Web UIからの基本的なON/OFF、調光、調色制御、仮想照明デバイスのシミュレーション。APIの基本設計。
    *   成果物: 動作するWebプロトタイプ、APIドキュメント。
2.  **フェーズ2: MVP (Minimum Viable Product) 開発**
    *   期間: 4ヶ月
    *   目標: 複数パネルのグループ制御、シーンプリセット、簡易スケジュール機能、安定したAPI提供。実際の有機ELパネル（評価用）との連携検討。
    *   成果物: MVP製品、技術検証レポート。
3.  **フェーズ3: 製品化に向けた開発**
    *   期間: 6ヶ月〜
    *   目標: パネルの量産設計、品質向上、法規制対応、施工性・メンテナンス性向上。
    *   成果物: 量産設計完了、各種認証取得。

---

## CoT証跡

### 背景と目的

ユーザーからの有機EL照明機器の新規開発要望に対し、具体的な製品像が不明確であったため、調査部AI「Mia」によるマーケティング調査が実施されました。その結果、有機EL照明が持つ独自の特性（薄型・面発光・高演色性・目に優しい光、フレキシブル性）が、特に高付加価値なB2B市場（高級ホテル、商業施設、美術館、医療・ヘルスケア）において高い潜在需要を持つことが明らかになりました。この調査結果を受け、新規事業開発部AI「Leo」は、具体的な製品コンセプトと要件を定義し、プロトタイプ開発の方向性を定めることを目的として本要件定義書を作成しました。

### データと推論プロセス

1.  **調査書の分析:**
    *   **市場規模:** 有機EL照明市場はニッチだが、CAGR 20%超の成長が予測されており、特に高付加価値分野での採用が期待されることを確認。これにより、初期開発はマス市場ではなく、特定のニッチ市場に焦点を当てるべきと判断。
    *   **成長ドライバー/トレンド:** 「薄型・軽量・フレキシブル」「面発光」「高演色性」「目に優しい光」「調光・調色」「スマートホーム・IoT連携」がキーワードとして抽出され、これらを製品の主要な機能・特性として定義する根拠とした。
    *   **競合分析:** LG Display, Konica Minoltaなどが主要競合であり、当社の差別化戦略として「特定のニッチ市場特化」「高品質・高付加価値」「デザイン性・カスタマイズ性」「既存技術とのシナジー」が推奨されていた。これはターゲットペルソナ選定と製品コンセプトに直結する。
    *   **ターゲットペルソナ:** 「高級ホテル/商業施設の内装デザイナー」が具体的に提示されており、その課題とニーズが詳細に記述されていた。これを基に、機能要件、非機能要件の多くを具体化する際の指針とした。特に「唯一無二の空間体験」「ブランドイメージを象徴するデザイン」「目に優しい上質な光質」「調光・調色機能」「省エネ・環境配慮」といったニーズは、プロダクトビジョンとコンセプトの核となった。

2.  **プロダクトビジョン・コンセプトの策定:**
    *   調査書で強調された有機ELの特性と、ペルソナのニーズを直接結びつけ、「デザインと統合」「上質な光体験」「スマートな光制御」「サステナビリティ」という4つのコンセプトを設定。これにより、製品の方向性を明確にした。

3.  **機能要件の具体化:**
    *   コンセプトとペルソナのニーズに基づき、照明パネル本体の特性（形状、光質、サイズ、寿命）と、制御システムの機能（ON/OFF、調光、調色、シーンプリセット、グループ制御、スケジュール）を詳細に定義。
    *   特に、内装デザイナーが求める「自由な形状」「空間に溶け込むデザイン」を実現するための薄型・フレキシブル性、そして「上質な光質」のための高演色性・ブルーライト低減を強調。
    *   「スマートホーム・IoT連携」のトレンドから、Webアプリケーションによる直感的なUIと、外部連携のためのAPI提供を必須要件とした。

4.  **非機能要件の定義:**
    *   B2B市場、特に高級施設での利用を想定し、性能、信頼性、保守性、拡張性、セキュリティ、運用、環境、コスト、法規制といった多角的な観点から要件を網羅的に定義。
    *   「長寿命」「低発熱」「水銀フリー」といった有機ELの特性を活かした環境要件や、B2Bにおける重要性が高い保守性・拡張性を重視した。
    *   プロトタイプ段階でどこまで対応するか、将来的な検討事項も明確にするため、スコープ外の機能も記述した。

5.  **開発フェーズとマイルストーン:**
    *   「緊急度：低」という要望分類と、新規事業としてのリスクを考慮し、PoC (プロトタイプ開発) からMVP、製品化へと段階的に進めるロードマップを設定。これにより、リソース配分と進捗管理の指針とした。

以上のプロセスを経て、マーケティング調査書で示された大まかな方向性を、具体的な製品要件と開発計画に落とし込みました。

---

## (2) 実装方針および主要なソースコード断片

### 1. 導入

本ドキュメントは、上記要件定義書に基づき、ECUANEST LuminaFlex OLED Solutionのプロトタイプ開発における実装方針と主要なコード断片を示すものです。初期段階では、Webアプリケーションを通じた仮想有機EL照明デバイスの制御を主眼に置き、主要な機能要件（ON/OFF、調光、調色、シーンプリセット）の実現可能性を検証します。

### 2. プロトタイプ開発の目的

*   有機EL照明の主要な制御機能（ON/OFF、明るさ、色温度）のWeb UIからの操作性を検証する。
*   仮想照明デバイスのバックエンドでの状態管理と、フロントエンドからのAPI連携の基本アーキテクチャを確立する。
*   将来的なIoT連携を見据えたAPI設計の基礎を築く。

### 3. 技術スタック

*   **フロントエンド:** Next.js (React), TypeScript, Tailwind CSS
    *   理由: 高い開発効率、SSR/SSGによるSEO性能（将来的な製品サイト連携）、モダンなUIフレームワーク。デザイン性を重視するためTailwind CSSを採用。
*   **バックエンド:** Node.js (Express), TypeScript
    *   理由: フロントエンドとの技術スタックの親和性、リアルタイム通信（WebSocket）の容易な実装、軽量でスケーラブルなAPIサーバー構築。
*   **リアルタイム通信:** WebSocket (Socket.IO)
    *   理由: 照明の状態変化をUIに即時反映するため。
*   **データストア:** インメモリまたはJSONファイル (プロトタイプのため)
    *   理由: データベースのセットアップコストを削減し、迅速な開発を優先。

### 4. 主要な機能の実装方針

#### 4.1. 仮想照明デバイスのバックエンド管理

*   Expressサーバー上で、複数の仮想有機EL照明デバイスの状態（`id`, `status: 'on'/'off'`, `brightness: 0-100`, `colorTemperature: 2700-6500`, `sceneId`）をメモリ内で管理します。
*   WebSocketを通じて、フロントエンドからの制御コマンドを受け付け、デバイスの状態を更新します。
*   状態が更新されるたびに、WebSocketを通じて接続されている全てのクライアントに最新の状態をブロードキャストします。

#### 4.2. Webアプリケーション (Next.js)

*   **ダッシュボード:** 全ての仮想照明デバイスの状態を一覧表示。
*   **個別制御パネル:** 各デバイスの詳細ページで、ON/OFFトグル、明るさスライダー、色温度スライダーを配置。
*   **シーンプリセット:** 複数のデバイスの状態をまとめて保存・適用する機能。
*   **API連携:** バックエンドのWebSocket APIを通じて、デバイスの状態取得と制御コマンド送信を行います。

#### 4.3. API設計 (RESTful & WebSocket)

*   **RESTful API (初期設定・非リアルタイム操作):**
    *   `GET /api/lights`: 全ての照明デバイスの状態を取得。
    *   `GET /api/lights/:id`: 特定の照明デバイスの状態を取得。
    *   `POST /api/scenes`: 新しいシーンを保存。
    *   `GET /api/scenes`: 保存されている全てのシーンを取得。
*   **WebSocket API (リアルタイム制御・状態更新):**
    *   クライアントからサーバーへ: `controlLight`, `applyScene` イベントで制御コマンドを送信。
    *   サーバーからクライアントへ: `lightStatusUpdate`, `sceneUpdate` イベントで状態変更をブロードキャスト。

### 5. 主要なソースコード断片

#### 5.1. バックエンド (Node.js/Express with Socket.IO)

`src/server.ts`

```typescript
// src/server.ts
import express from 'express';
import http from 'http';
import { Server as SocketIOServer } from 'socket.io';
import cors from 'cors';

const app = express();
const server = http.createServer(app);
const io = new SocketIOServer(server, {
  cors: {
    origin: "http://localhost:3000", // Next.jsアプリのオリジン
    methods: ["GET", "POST"]
  }
});

app.use(cors());
app.use(express.json());

interface LightState {
  id: string;
  name: string;
  status: 'on' | 'off';
  brightness: number; // 0-100
  colorTemperature: number; // 2700-6500K
  sceneId?: string;
}

interface Scene {
  id: string;
  name: string;
  lightStates: { lightId: string; brightness: number; colorTemperature: number }[];
}

// 仮想照明デバイスの状態
const lights: LightState[] = [
  { id: 'oled-001', name: 'Lobby Panel A', status: 'off', brightness: 50, colorTemperature: 4000 },
  { id: 'oled-002', name: 'Lobby Panel B', status: 'on', brightness: 80, colorTemperature: 3000 },
  { id: 'oled-003', name: 'Corridor Flex', status: 'on', brightness: 60, colorTemperature: 5000 },
];

// 仮想シーン
const scenes: Scene[] = [
  {
    id: 'scene-relax',
    name: 'Relax Mode',
    lightStates: [
      { lightId: 'oled-001', brightness: 30, colorTemperature: 2700 },
      { lightId: 'oled-002', brightness: 40, colorTemperature: 3000 },
      { lightId: 'oled-003', brightness: 20, colorTemperature: 2700 },
    ],
  },
  {
    id: 'scene-bright',
    name: 'Bright Mode',
    lightStates: [
      { lightId: 'oled-001', brightness: 90, colorTemperature: 6000 },
      { lightId: 'oled-002', brightness: 80, colorTemperature: 5500 },
      { lightId: 'oled-003', brightness: 70, colorTemperature: 6500 },
    ],
  },
];

// RESTful API
app.get('/api/lights', (req, res) => {
  res.json(lights);
});

app.get('/api/lights/:id', (req, res) => {
  const light = lights.find(l => l.id === req.params.id);
  if (light) {
    res.json(light);
  } else {
    res.status(404).json({ message: 'Light not found' });
  }
});

app.get('/api/scenes', (req, res) => {
  res.json(scenes);
});

app.post('/api/scenes', (req, res) => {
  const newScene: Scene = {
    id: `scene-${Date.now()}`,
    name: req.body.name,
    lightStates: req.body.lightStates,
  };
  scenes.push(newScene);
  io.emit('sceneUpdate', scenes); // シーンリストの更新をブロードキャスト
  res.status(201).json(newScene);
});

// WebSocket (Socket.IO) 接続ハンドリング
io.on('connection', (socket) => {
  console.log('A user connected:', socket.id);

  // 照明制御コマンド
  socket.on('controlLight', (payload: { id: string; status?: 'on' | 'off'; brightness?: number; colorTemperature?: number }) => {
    const light = lights.find(l => l.id === payload.id);
    if (light) {
      if (payload.status !== undefined) light.status = payload.status;
      if (payload.brightness !== undefined) light.brightness = Math.max(0, Math.min(100, payload.brightness));
      if (payload.colorTemperature !== undefined) light.colorTemperature = Math.max(2700, Math.min(6500, payload.colorTemperature));
      light.sceneId = undefined; // 個別制御時はシーン適用を解除
      io.emit('lightStatusUpdate', light); // 全クライアントに更新をブロードキャスト
    }
  });

  // シーン適用コマンド
  socket.on('applyScene', (sceneId: string) => {
    const scene = scenes.find(s => s.id === sceneId);
    if (scene) {
      scene.lightStates.forEach(sceneLight => {
        const light = lights.find(l => l.id === sceneLight.lightId);
        if (light) {
          light.status = 'on'; // シーン適用時はON
          light.brightness = sceneLight.brightness;
          light.colorTemperature = sceneLight.colorTemperature;
          light.sceneId = scene.id;
        }
      });
      // 全てのライトの更新をブロードキャスト
      lights.forEach(light => io.emit('lightStatusUpdate', light));
    }
  });

  socket.on('disconnect', () => {
    console.log('User disconnected:', socket.id);
  });
});

const PORT = process.env.PORT || 3001;
server.listen(PORT, () => {
  console.log(`Backend server running on port ${PORT}`);
});
```

#### 5.2. フロントエンド (Next.js/React)

`src/app/page.tsx` (ダッシュボードページ)

```tsx
// src/app/page.tsx
'use client';

import { useEffect, useState } from 'react';
import io from 'socket.io-client';
import { Slider } from '@/components/ui/slider'; // shadcn/ui を想定
import { Switch } from '@/components/ui/switch'; // shadcn/ui を想定
import { Button } from '@/components/ui/button'; // shadcn/ui を想定
import { Card, CardContent, CardHeader, CardTitle } from '@/components/ui/card'; // shadcn/ui を想定

// 型定義（バックエンドと共通化を推奨）
interface LightState {
  id: string;
  name: string;
  status: 'on' | 'off';
  brightness: number;
  colorTemperature: number;
  sceneId?: string;
}

interface Scene {
  id: string;
  name: string;
  lightStates: { lightId: string; brightness: number; colorTemperature: number }[];
}

const socket = io('http://localhost:3001'); // バックエンドのURL

export default function Dashboard() {
  const [lights, setLights] = useState<LightState[]>([]);
  const [scenes, setScenes] = useState<Scene[]>([]);

  useEffect(() => {
    // 初期データ取得 (RESTful API)
    fetch('http://localhost:3001/api/lights')
      .then(res => res.json())
      .then(setLights);
    fetch('http://localhost:3001/api/scenes')
      .then(res => res.json())
      .then(setScenes);

    // WebSocketでリアルタイム更新を購読
    socket.on('lightStatusUpdate', (updatedLight: LightState) => {
      setLights(prevLights =>
        prevLights.map(light => (light.id === updatedLight.id ? updatedLight : light))
      );
    });

    socket.on('sceneUpdate', (updatedScenes: Scene[]) => {
      setScenes(updatedScenes);
    });

    return () => {
      socket.off('lightStatusUpdate');
      socket.off('sceneUpdate');
    };
  }, []);

  const handleToggle = (id: string, checked: boolean) => {
    socket.emit('controlLight', { id, status: checked ? 'on' : 'off' });
  };

  const handleBrightnessChange = (id: string, value: number[]) => {
    socket.emit('controlLight', { id, brightness: value[0] });
  };

  const handleColorTemperatureChange = (id: string, value: number[]) => {
    socket.emit('controlLight', { id, colorTemperature: value[0] });
  };

  const handleApplyScene = (sceneId: string) => {
    socket.emit('applyScene', sceneId);
  };

  return (
    <div className="container mx-auto p-8">
      <h1 className="text-4xl font-bold mb-8">ECUANEST LuminaFlex Dashboard</h1>

      <section className="mb-12">
        <h2 className="text-2xl font-semibold mb-4">Scenes</h2>
        <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
          {scenes.map(scene => (
            <Card key={scene.id}>
              <CardHeader>
                <CardTitle>{scene.name}</CardTitle>
              </CardHeader>
              <CardContent>
                <Button onClick={() => handleApplyScene(scene.id)} className="w-full">
                  Apply Scene
                </Button>
              </CardContent>
            </Card>
          ))}
        </div>
      </section>

      <section>
        <h2 className="text-2xl font-semibold mb-4">Individual Light Control</h2>
        <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
          {lights.map(light => (
            <Card key={light.id}>
              <CardHeader className="flex flex-row items-center justify-between space-y-0 pb-2">
                <CardTitle className="text-lg font-medium">{light.name}</CardTitle>
                <Switch
                  checked={light.status === 'on'}
                  onCheckedChange={(checked) => handleToggle(light.id, checked)}
                />
              </CardHeader>
              <CardContent>
                <div className="space-y-4">
                  <div>
                    <label className="text-sm font-medium leading-none peer-disabled:cursor-not-allowed peer-disabled:opacity-70">
                      Brightness: {light.brightness}%
                    </label>
                    <Slider
                      min={0}
                      max={100}
                      step={1}
                      value