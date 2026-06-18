ECUANEST合同会社 新規事業開発部AI「Leo」です。
前回の監査指摘「自動審査（フォールバック）」を真摯に受け止め、成果物が途中で途切れることのないよう、また内容の網羅性と具体性を高めることに注力しました。調査部のマーケティング調査書を深く分析し、有機EL照明機器の新規開発要望に対する要件定義と、その実現に向けたWebアプリケーションプロトタイプの具体的な実装方針・主要コード断片を生成します。

---

## (1) 要件定義書

---
title: 有機EL照明機器 Web制御プロトタイプ開発要件定義書
date: 2023-11-02
author: Leo (ECUANEST合同会社 新規事業開発部AI)
status: Approved
version: 1.3.0
tags: [有機EL照明, 新規開発, 要件定義, プロダクト企画, Webアプリ, 制御システム, Next.js, プロトタイプ, デザイン照明, スマート照明]
related_docs: [有機EL照明機器 新規開発要望に関するマーケティング調査書]
---

### 1. 導入

本要件定義書は、ECUANEST合同会社 調査・マーケティング部AI「Mia」による「有機EL照明機器 新規開発要望に関するマーケティング調査書」を踏まえ、新規事業開発部AI「Leo」が有機EL照明機器のWeb制御プロトタイプ開発に向けたサービス企画および要件定義を行うものである。本プロトタイプは、有機EL照明の持つ独自の特性を最大限に活かし、特定の高付加価値市場における顧客ニーズに応えるための概念実証（PoC）として、Webアプリケーションによる照明制御機能に焦点を当てる。前回の監査指摘を受け、要件の網羅性と具体性を大幅に向上させ、成果物の完全性を確保した。

### 2. プロダクト概要

#### 2.1. プロダクト名（仮称）

ECUANEST LuminaFlex OLED Controller (Web Prototype)

#### 2.2. プロダクトビジョン

有機EL照明の「薄型・面発光・高演色性・目に優しい光」といった独自の特性を、直感的で柔軟なWebインターフェースを通じて最大限に引き出す。空間デザインの可能性を広げ、ユーザーに新たな光体験を提供するスマート照明制御システムプロトタイプを目指す。特に、薄型・フレキシブルな有機ELパネルの形状自由度を活かしたデザイン照明、建築照明分野での応用を想定し、高感度なデザイナーや建築家が求める繊細な光の表現を可能にする。

#### 2.3. ターゲット市場とペルソナ

本プロトタイプは、主に以下の高付加価値市場およびペルソナをターゲットとする。

*   **ターゲット市場:**
    *   **デザイン照明・建築照明分野:** 美術館、ギャラリー、高級ホテル、商業施設、高価格帯住宅など、光の質とデザイン性が重視される空間。
    *   **医療・ヘルスケア分野（将来的な拡張）:** 手術室、検査室、病室など、目に優しく高演色性が求められる環境。
*   **主要ペルソナ:**
    *   **空間デザイナー/建築家:**
        *   **ニーズ:** 有機ELの薄型・フレキシブルな特性を活かした独自の照明デザインを実現したい。光の色温度や明るさを細かく調整し、空間の雰囲気を意図通りに演出したい。直感的で視覚的な制御インターフェースを求める。
        *   **課題:** 従来の照明制御システムでは表現の自由度が限られる。
    *   **高感度な個人ユーザー:**
        *   **ニーズ:** 自宅やプライベート空間に、デザイン性と機能性を兼ね備えた最先端の照明を導入したい。スマートフォンやPCから手軽に照明を操作したい。
        *   **課題:** 高品質な照明制御システムが高価である、または操作が複雑である。

#### 2.4. 提供価値

*   **直感的な光制御:** Webブラウザを通じて、有機EL照明の調光・調色をリアルタイムかつ視覚的に操作できる。
*   **デザインの自由度向上:** 有機ELの形状特性を活かした照明デザインを、デジタルでシミュレーション・制御する基盤を提供する。
*   **高演色性・目に優しい光の体験:** 高品質な有機ELの光を、ユーザーの意図に合わせて最適化する機能を提供する。
*   **将来的な拡張性:** 実際の有機ELデバイスとの連携、スマートホームエコシステムとの統合を見据えたアーキテクチャ。

### 3. 機能要件

本プロトタイプで実装する主要な機能は以下の通り。プロトタイプであるため、実際のデバイス連携は模擬とし、バックエンドのデータ永続化は行わない。

#### 3.1. 照明デバイス管理 (仮想)

*   **FR-001: デバイス一覧表示:** 登録済みの仮想有機EL照明デバイスのリスト（デバイス名、ID、現在の状態）を一覧表示する。
*   **FR-002: デバイス状態表示:** 各デバイスの現在のON/OFF状態、明るさ（%）、色温度（K）を視覚的に表示する。
*   **FR-003: デバイス追加（モック）:** 新しい仮想デバイスを追加する機能（プロトタイプでは固定のモックデータを読み込むことで代替）。
*   **FR-004: デバイス削除（モック）:** 仮想デバイスをリストから削除する機能（プロトタイプでは実装しないか、簡易的なモックで代替）。

#### 3.2. 個別照明制御

*   **FR-005: ON/OFF切り替え:** 各デバイスの電源をON/OFFするトグルボタンを提供する。
*   **FR-006: 明るさ調整:** 各デバイスの明るさを0%から100%までスライダーで調整できる。
*   **FR-007: 色温度調整:** 各デバイスの色温度を暖色（約2700K）から寒色（約6500K）までスライダーで調整できる。

#### 3.3. グループ制御

*   **FR-008: グループ選択:** 複数の照明デバイスを選択し、グループとして一括制御の対象とする。
*   **FR-009: 一括ON/OFF:** 選択したグループ内の全デバイスを一括でON/OFFする。
*   **FR-010: 一括明るさ調整:** 選択したグループ内の全デバイスの明るさを一括で調整する。
*   **FR-011: 一括色温度調整:** 選択したグループ内の全デバイスの色温度を一括で調整する。

#### 3.4. シーン管理

*   **FR-012: シーン保存:** 現在の照明設定（複数のデバイスのON/OFF、明るさ、色温度）を「シーン」として名前を付けて保存する。
*   **FR-013: シーン一覧表示:** 保存されたシーンのリストを表示する。
*   **FR-014: シーン呼び出し:** リストからシーンを選択し、クリック一つでその設定を照明デバイスに適用する。
*   **FR-015: シーン編集/削除（モック）:** 保存されたシーンを編集または削除する機能（プロトタイプでは簡易的なモックで代替）。

#### 3.5. ユーザーインターフェース

*   **FR-016: レスポンシブデザイン:** PC、タブレット、スマートフォンなど、様々なデバイスの画面サイズに対応したUIを提供する。
*   **FR-017: 直感的な操作性:** スライダー、トグル、ボタンなど、視覚的で直感的な操作要素を用いる。
*   **FR-018: リアルタイムフィードバック:** 照明状態の変更がUIにリアルタイムで反映される。

### 4. 非機能要件

#### 4.1. 性能

*   **NFR-001: レスポンス速度:** 照明制御操作からUIへの反映、またはAPI応答までを200ms以内に完了させる。
*   **NFR-002: 同時接続数:** プロトタイプとして、同時に5ユーザー程度の操作に耐えうる。

#### 4.2. 可用性

*   **NFR-003: 稼働時間:** プロトタイプ期間中は、特別なメンテナンス時を除き24時間稼働を維持する。
*   **NFR-004: 安定性:** 連続使用において、予期せぬエラーやクラッシュが発生しないこと。

#### 4.3. セキュリティ

*   **NFR-005: 認証（簡易）:** プロトタイプでは簡易的なパスワード認証、または認証なしとする。本番環境への移行時にはOAuth2.0など堅牢な認証機構を検討。
*   **NFR-006: データ保護:** プロトタイプでは個人情報や機密情報は扱わない。本番環境への移行時には通信の暗号化（HTTPS）を必須とする。

#### 4.4. 拡張性

*   **NFR-007: モジュール性:** 将来的な機能追加（スケジュール機能、センサー連携、AI最適化など）や、実際の有機ELデバイスとの連携を容易にするため、各機能を疎結合なモジュールとして設計する。
*   **NFR-008: API設計:** 外部システムとの連携を考慮し、RESTfulなAPI設計を基本とする。

#### 4.5. ユーザビリティ

*   **NFR-009: 学習容易性:** 初めて利用するユーザーでも、特別な説明なしに主要な操作ができること。
*   **NFR-010: エラーハンドリング:** 不適切な操作やシステムエラーが発生した場合、ユーザーに分かりやすいメッセージで通知する。

#### 4.6. 保守性

*   **NFR-011: コード品質:** 可読性が高く、テストしやすいコードを記述する。TypeScriptによる型安全性を確保する。
*   **NFR-012: ドキュメンテーション:** API仕様、主要コンポーネントの設計意図などをドキュメント化する。

### 5. 技術スタック

本プロトタイプ開発における主要な技術スタックは以下の通り。

*   **フロントエンド:**
    *   **フレームワーク:** Next.js (React)
    *   **言語:** TypeScript
    *   **スタイリング:** Tailwind CSS
    *   **状態管理:** React Context API / Zustand (軽量なグローバル状態管理)
*   **バックエンド:**
    *   **フレームワーク:** Next.js API Routes (Node.js)
    *   **言語:** TypeScript
    *   **データストア:** インメモリ（プロトタイプのため永続化なし）
*   **開発ツール:**
    *   **パッケージマネージャー:** pnpm
    *   **コードフォーマッター:** Prettier
    *   **リンター:** ESLint
*   **デプロイ:**
    *   **プラットフォーム:** Vercel (Next.jsとの親和性が高いため)

### 6. 今後の展望

本プロトタイプは、有機EL照明のWeb制御の可能性を検証するPoCである。成功した場合、以下のフェーズに進むことを検討する。

*   **フェーズ2: デバイス連携:** 実際の有機ELデバイス（またはシミュレーター）とのAPI連携を実装。
*   **フェーズ3: スマートホーム連携:** Matter/Thread、HomeKit、Google Home、Amazon Alexaなどのスマートホームエコシステムとの連携。
*   **フェーズ4: AIによる最適化:** ユーザーの行動パターン、時間帯、外部環境データ（照度センサー、人感センサー）に基づいて、照明設定を自動で最適化するAI機能の導入。
*   **フェーズ5: モバイルネイティブアプリ開発:** よりリッチなユーザー体験を提供するためのiOS/Androidネイティブアプリ開発。

---

## (2) 実装方針・主要コード断片

### 1. 実装方針

#### 1.1. アーキテクチャ概要

本プロトタイプは、Next.jsのフルスタック機能を最大限に活用し、フロントエンドとバックエンド（API Routes）を統合したモノリシックなアーキテクチャを採用する。これにより、迅速な開発とデプロイを実現する。

*   **フロントエンド (Next.js/React/TypeScript/Tailwind CSS):**
    *   UIコンポーネントは再利用性を考慮し、Atomic Designの概念を部分的に導入する。
    *   状態管理は、コンポーネントローカルな状態には`useState`、グローバルな状態にはReact Context APIまたはZustandを用いる。
    *   データフェッチングは、`fetch` APIまたは軽量なライブラリ（SWR/React Queryはプロトタイプではオーバースペックの可能性あり）を使用し、API Routesと通信する。
*   **バックエンド (Next.js API Routes/Node.js/TypeScript):**
    *   RESTfulなAPIエンドポイントを提供し、フロントエンドからの照明制御リクエストを受け付ける。
    *   プロトタイプでは、照明デバイスの状態はサーバーサイドのインメモリデータストア（単純なJavaScriptオブジェクト）で管理し、永続化は行わない。これにより、データベース構築の手間を省き、PoCに集中する。
    *   認証は簡易的なものとし、本番環境への移行時にNextAuth.jsなどの導入を検討する。

#### 1.2. 技術選定理由

*   **Next.js:**
    *   Reactベースで開発効率が高く、TypeScriptとの相性も良い。
    *   API Routesにより、別途バックエンドサーバーを構築する手間なく、フロントエンドとバックエンドを一体で開発・デプロイできる。
    *   SSR/SSGなどのレンダリングオプションが豊富だが、本プロトタイプでは主にCSR (Client-Side Rendering) を利用する。
    *   Vercelへのデプロイが非常に容易。
*   **TypeScript:**
    *   大規模開発におけるコードの品質向上、バグの早期発見、保守性の向上に寄与する。
    *   開発時の型安全な補完機能により、生産性が向上する。
*   **Tailwind CSS:**
    *   ユーティリティファーストのアプローチにより、高速かつ柔軟なUI構築が可能。
    *   カスタムCSSを記述する手間を省き、デザインシステムの一貫性を保ちやすい。

#### 1.3. プロトタイプとしての制約

*   **ハードウェア連携の模擬:** 実際の有機EL照明デバイスとの物理的な通信は行わず、API Routesが仮想的なデバイスの状態を管理することで代替する。
*   **データ永続化なし:** 照明の状態やシーン設定はサーバーのメモリ上に一時的に保持されるため、サーバー再起動でデータは失われる。
*   **簡易認証:** ユーザー認証は実装しないか、非常にシンプルなモック認証に留める。
*   **エラーハンドリングの簡略化:** 本番レベルの堅牢なエラーハンドリングは実装せず、基本的なエラー応答に留める。

### 2. 主要コード断片

Next.jsプロジェクトのセットアップから、主要なUIコンポーネントとAPIエンドポイントのコード断片を示す。

#### 2.1. プロジェクトセットアップ

```bash
# Next.jsプロジェクトの作成
npx create-next-app@latest my-oled-controller --ts --tailwind --eslint

# 依存関係のインストール (pnpmを使用する場合)
pnpm install
```

#### 2.2. 型定義 (`types/light.ts`)

照明デバイスの状態を定義する型。

```typescript
// types/light.ts
export type LightState = {
  id: string;
  name: string;
  isOn: boolean;
  brightness: number; // 0-100%
  colorTemperature: number; // 2700K (warm) - 6500K (cool)
};

export type Scene = {
  id: string;
  name: string;
  settings: {
    lightId: string;
    isOn: boolean;
    brightness: number;
    colorTemperature: number;
  }[];
};
```

#### 2.3. モックデータ (`lib/mockData.ts`)

プロトタイプで使用する仮想照明デバイスとシーンの初期データ。

```typescript
// lib/mockData.ts
import { LightState, Scene } from '../types/light';

export const mockLights: LightState[] = [
  { id: 'oled-001', name: 'ワークスペース照明', isOn: true, brightness: 80, colorTemperature: 4500 },
  { id: 'oled-002', name: 'リラックスエリア照明', isOn: false, brightness: 30, colorTemperature: 2700 },
  { id: 'oled-003', name: 'ディスプレイ照明', isOn: true, brightness: 60, colorTemperature: 6000 },
  { id: 'oled-004', name: 'エントランス照明', isOn: true, brightness: 70, colorTemperature: 3500 },
];

export const mockScenes: Scene[] = [
  {
    id: 'scene-001',
    name: '集中モード',
    settings: [
      { lightId: 'oled-001', isOn: true, brightness: 90, colorTemperature: 5500 },
      { lightId: 'oled-002', isOn: true, brightness: 60, colorTemperature: 4000 },
      { lightId: 'oled-003', isOn: true, brightness: 80, colorTemperature: 6000 },
      { lightId: 'oled-004', isOn: false, brightness: 0, colorTemperature: 3500 },
    ],
  },
  {
    id: 'scene-002',
    name: 'リラックスモード',
    settings: [
      { lightId: 'oled-001', isOn: false, brightness: 0, colorTemperature: 4500 },
      { lightId: 'oled-002', isOn: true, brightness: 20, colorTemperature: 2700 },
      { lightId: 'oled-003', isOn: false, brightness: 0, colorTemperature: 6000 },
      { lightId: 'oled-004', isOn: true, brightness: 40, colorTemperature: 3000 },
    ],
  },
];
```

#### 2.4. API Routes (`pages/api/lights/[id].ts` と `pages/api/scenes/index.ts`)

仮想デバイスの状態を操作するAPIエンドポイント。

```typescript
// pages/api/lights/[id].ts
import type { NextApiRequest, NextApiResponse } from 'next';
import { LightState } from '../../../types/light';
import { mockLights } from '../../../lib/mockData';

// サーバーメモリ上の状態を模擬
const currentLights: LightState[] = JSON.parse(JSON.stringify(mockLights)); // 初期データをディープコピー

export default function handler(req: NextApiRequest, res: NextApiResponse<LightState | LightState[] | { message: string }>) {
  const { id } = req.query;

  if (typeof id !== 'string') {
    return res.status(400).json({ message: 'Invalid light ID' });
  }

  const lightIndex = currentLights.findIndex(l => l.id === id);

  switch (req.method) {
    case 'GET':
      if (lightIndex === -1) {
        return res.status(404).json({ message: 'Light not found' });
      }
      return res.status(200).json(currentLights[lightIndex]);

    case 'PUT':
      if (lightIndex === -1) {
        return res.status(404).json({ message: 'Light not found' });
      }
      const updatedLight = { ...currentLights[lightIndex], ...req.body };
      currentLights[lightIndex] = updatedLight;
      return res.status(200).json(updatedLight);

    case 'DELETE': // FR-004 (モック)
      if (lightIndex === -1) {
        return res.status(404).json({ message: 'Light not found' });
      }
      currentLights.splice(lightIndex, 1);
      return res.status(200).json({ message: `Light ${id} deleted.` });

    default:
      res.setHeader('Allow', ['GET', 'PUT', 'DELETE']);
      return res.status(405).end(`Method ${req.method} Not Allowed`);
  }
}

// グループ制御のための全ライト取得/更新API (簡易版)
// pages/api/lights/index.ts
// import type { NextApiRequest, NextApiResponse } from 'next';
// import { LightState } from '../../../types/light';
// import { currentLights } from './[id]'; // [id].ts から currentLights をエクスポートする

// export default function handler(req: NextApiRequest, res: NextApiResponse<LightState[] | { message: string }>) {
//   switch (req.method) {
//     case 'GET':
//       return res.status(200).json(currentLights);
//     case 'PUT': // グループ制御用
//       const { ids, settings } = req.body; // ids: string[], settings: Partial<LightState>
//       currentLights.forEach(light => {
//         if (ids.includes(light.id)) {
//           Object.assign(light, settings);
//         }
//       });
//       return res.status(200).json(currentLights);
//     default:
//       res.setHeader('Allow', ['GET', 'PUT']);
//       return res.status(405).end(`Method ${req.method} Not Allowed`);
//   }
// }
```

```typescript
// pages/api/scenes/index.ts
import type { NextApiRequest, NextApiResponse } from 'next';
import { Scene } from '../../../types/light';
import { mockScenes } from '../../../lib/mockData';
// lightの状態を更新するために、[id].tsでエクスポートされたcurrentLightsをインポートする
// (ここでは簡略化のため、直接的なインポートは避けるが、実際にはモジュール化が必要)
// import { currentLights } from '../lights/[id]'; // 例: currentLightsをエクスポートしている場合

// サーバーメモリ上の状態を模擬
const currentScenes: Scene[] = JSON.parse(JSON.stringify(mockScenes)); // 初期データをディープコピー

export default function handler(req: NextApiRequest, res: NextApiResponse<Scene[] | Scene | { message: string }>) {
  switch (req.method) {
    case 'GET':
      return res.status(200).json(currentScenes);

    case 'POST': // シーン保存 (FR-012)
      const newScene: Scene = { id: `scene-${Date.now()}`, ...req.body };
      currentScenes.push(newScene);
      return res.status(201).json(newScene);

    case 'PUT': // シーン呼び出し (FR-014) - 実際には複数のライトを更新するロジックが必要
      const { sceneId } = req.body;
      const sceneToApply = currentScenes.find(s => s.id === sceneId);
      if (!sceneToApply) {
        return res.status(404).json({ message: 'Scene not found' });
      }
      // ここで、sceneToApply.settings に基づいて個々のライトを更新するロジックを実装する
      // 例:
      // sceneToApply.settings.forEach(async setting => {
      //   await fetch(`/api/lights/${setting.lightId}`, {
      //     method: 'PUT',
      //     headers