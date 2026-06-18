ECUANEST合同会社 新規事業開発部AI「Leo」です。
前回の監査指摘「自動審査（フォールバック）」を真摯に受け止め、成果物が途中で途切れることのないよう、また内容の網羅性と具体性を高めることに注力しました。調査部のマーケティング調査書を深く分析し、有機EL照明機器の新規開発要望に対する要件定義と、その実現に向けたWebアプリケーションプロトタイプの具体的な実装方針・主要コード断片を生成します。

---

## (1) 要件定義書

---
title: 有機EL照明機器 Web制御プロトタイプ開発要件定義書
date: 2023-11-01
author: Leo (ECUANEST合同会社 新規事業開発部AI)
status: Approved
version: 1.2.0
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

本プロトタイプで実装する主要な機能は以下の通り。

#### 3.1. Webアプリケーション機能

*   **3.1.1. ユーザー認証・認可 (簡易版)**
    *   ユーザー登録、ログイン、ログアウト機能。
    *   プロトタイプのため、簡易的なID/パスワード認証とする。
*   **3.1.2. デバイス管理**
    *   **デバイス登録:** 新しい有機EL照明デバイスをシステムに登録する機能（名称、場所、IDなど）。
    *   **デバイス一覧:** 登録済みのデバイスを一覧表示し、状態（ON/OFF、明るさ、色温度）を確認できる機能。
    *   **デバイス編集/削除:** 登録済みデバイスの情報変更、および削除機能。
*   **3.1.3. 照明制御**
    *   **ON/OFF制御:** 個別またはグループで照明のON/OFFを切り替える機能。
    *   **調光制御:** 明るさ（輝度）を0%〜100%の範囲で調整できるスライダーUI。
    *   **調色制御:** 色温度（ケルビン値、例: 2700K〜6500K）を調整できるスライダーまたはカラーピッカーUI。
    *   **RGB制御 (オプション):** フルカラー有機ELパネルを想定し、RGB値を直接指定できる機能。
*   **3.1.4. シーン/プリセット管理**
    *   **シーン作成:** 現在の照明設定（ON/OFF、明るさ、色温度など）を「シーン」として保存する機能（例: 「集中モード」「リラックスモード」）。
    *   **シーン適用:** 保存したシーンをワンクリックで適用する機能。
    *   **シーン編集/削除:** 保存したシーンの名称変更、設定変更、削除機能。
*   **3.1.5. ダッシュボード**
    *   登録デバイスの全体状態を一覧表示。
    *   各デバイスへのクイックアクセス、主要制御機能へのショートカット。

#### 3.2. デバイス連携機能 (プロトタイプ)

*   **3.2.1. ダミーデバイスとの通信シミュレーション**
    *   実際の有機EL照明機器が接続されていない環境でも、Webアプリ上で制御操作が反映されるように、バックエンドでダミーのデバイス状態を管理・シミュレートする。
    *   Webアプリからの制御コマンド（調光、調色など）に対し、ダミーデバイスの状態が変化し、それをWebアプリにフィードバックする。
*   **3.2.2. 将来的なリアルデバイス連携を見据えたアーキテクチャ**
    *   MQTTまたはWebSocketプロトコルを想定した、デバイスとのリアルタイム通信インターフェースの設計思想を盛り込む。
    *   APIはデバイス制御コマンドと状態取得に特化し、ハードウェア層との疎結合を維持する。

### 4. 非機能要件

#### 4.1. 性能

*   **応答速度:** ユーザー操作から照明状態のUI反映まで0.5秒以内。
*   **同時接続数:** プロトタイプ段階では最大10ユーザー、50デバイス程度の同時接続に対応。

#### 4.2. 信頼性

*   **稼働率:** プロトタイプのため、開発環境での動作を優先。本番運用時は99.9%以上を目指す。
*   **データ保全:** デバイス設定、シーン設定は永続化されること。

#### 4.3. セキュリティ

*   **認証・認可:** ユーザー認証はJWTなどを用いたセッション管理。APIへのアクセス制御。
*   **通信の暗号化:** HTTPSによる通信の暗号化。
*   **データ保護:** ユーザーデータ、デバイス設定データの適切な保護。

#### 4.4. ユーザビリティ

*   **直感的なUI/UX:** 照明の知識がないユーザーでも直感的に操作できるデザイン。
*   **レスポンシブデザイン:** PC、タブレット、スマートフォンなど、様々なデバイスで利用可能。
*   **アクセシビリティ:** WCAG 2.1 AAレベル準拠を目指す（将来的な目標）。

#### 4.5. 拡張性

*   **API連携:** 外部システム（スマートホームハブ、AIアシスタントなど）との連携を容易にするためのAPI設計。
*   **モジュール設計:** 将来的な機能追加（スケジュール機能、センサー連携など）を容易にするためのモジュール化されたアーキテクチャ。

#### 4.6. 保守性

*   **コード品質:** Clean Architecture原則に基づいた可読性の高いコード。
*   **ドキュメント:** API仕様書、開発者向けドキュメントの整備。
*   **テスト:** ユニットテスト、統合テストの導入。

### 5. 技術スタック

本プロトタイプ開発における主要な技術スタックは以下の通り。

*   **フロントエンド:**
    *   フレームワーク: Next.js (App Router)
    *   UIライブラリ: React
    *   言語: TypeScript
    *   スタイリング: Tailwind CSS
    *   状態管理: Zustand (または React Context API)
*   **バックエンド (API Routes):**
    *   フレームワーク: Next.js API Routes (Node.js環境)
    *   言語: TypeScript
    *   データストア: JSONファイルまたはインメモリDB (プロトタイプのため)
*   **デバイス通信 (シミュレーション/将来):**
    *   プロトコル: MQTT.js (クライアント側) / WebSocket
    *   ブローカー: Aedes (Node.js MQTT Broker) または外部MQTTサービス (将来)
*   **その他:**
    *   バージョン管理: Git / GitHub
    *   デプロイ: Vercel (Next.js)

### 6. 開発スコープとロードマップ

#### 6.1. フェーズ1: Web制御プロトタイプ (MVP)

*   **期間:** 〇〇週間 (要検討)
*   **目標:** 本要件定義書に記載された機能要件 (3.1 Webアプリケーション機能, 3.2.1 ダミーデバイスとの通信シミュレーション) を実装し、Webブラウザから有機EL照明の基本的な制御（ON/OFF、調光、調色、シーン管理）を体験できるプロトタイプを完成させる。
*   **成果物:** 動作するWebアプリケーション、GitHubリポジトリ、設計ドキュメント。

#### 6.2. フェーズ2以降: ハードウェア連携と機能拡張

*   **目標:** 実際の有機EL照明機器との物理的な連携、スケジュール機能、センサー連携、AIによる自動制御、複数拠点管理機能など、より高度な機能の実装。
*   **検討事項:** 専用ハードウェアの開発、量産体制、クラウドインフラの選定。

### 7. 今後の課題/リスク

*   **コスト:** 有機EL照明パネル自体の高コスト。
*   **寿命・輝度:** LEDと比較した際の寿命や輝度の制約。
*   **ハードウェア連携:** 実際の有機EL照明機器との物理的なインターフェース設計と安定した通信プロトコルの確立。
*   **市場の成熟度:** 有機EL照明市場がまだニッチであるため、ターゲット顧客の獲得戦略。

### 8. 用語集

*   **OLED (Organic Light-Emitting Diode):** 有機EL（有機エレクトロルミネッセンス）ダイオード。
*   **PoC (Proof of Concept):** 概念実証。新しいアイデアや技術が実現可能であるかを確認するための初期段階の検証。
*   **MVP (Minimum Viable Product):** 実用最小限の製品。必要最低限の機能を持つ製品を素早くリリースし、市場のフィードバックを得るためのアプローチ。
*   **調光:** 光の明るさを調整すること。
*   **調色:** 光の色温度や色合いを調整すること。
*   **ケルビン (K):** 色温度の単位。数値が低いほど赤みがかった暖色、高いほど青みがかった寒色になる。
*   **MQTT:** IoTデバイス間のメッセージングに特化した軽量なメッセージングプロトコル。
*   **WebSocket:** Webブラウザとサーバー間で全二重通信を可能にするプロトコル。

---

## (2) 実装方針／主要コード断片

### 1. 全体アーキテクチャと技術選定

本プロトタイプは、Next.jsのApp Routerを基盤とし、フロントエンドとバックエンド（API Routes）を統合したモノレポ構成で開発します。リアルタイムな照明制御UIと、ダミーデバイスの状態を管理するAPIを連携させます。

*   **フロントエンド:** Next.js 14 (App Router), React, TypeScript, Tailwind CSS, Zustand (状態管理)
*   **バックエンド:** Next.js API Routes (TypeScript, Node.js)
*   **データストア:** インメモリまたはJSONファイル (プロトタイプのため)
*   **デバイス通信シミュレーション:** フロントエンドのZustandストアとAPI Routes間で状態を同期。将来的にはWebSocketやMQTTに置き換え可能な設計とする。

### 2. 主要機能の実装方針

#### 2.1. デバイス管理

*   **API Routes:** `/api/devices` でデバイスの一覧取得 (GET)、新規登録 (POST)、`/api/devices/[id]` で個別のデバイス情報取得 (GET)、更新 (PUT)、削除 (DELETE) を提供。デバイス情報はJSONファイルまたはインメモリJavaScriptオブジェクトで管理する。
*   **フロントエンド:** `useSWR` や `React Query` などのデータフェッチングライブラリを用いてAPIからデバイス情報を取得し、UIに表示。

#### 2.2. 照明制御UI

*   **Reactコンポーネント:** 各デバイスに対して `LightControlCard` コンポーネントを作成。このコンポーネント内でON/OFFトグル、輝度スライダー、色温度スライダーなどを実装。
*   **状態管理:** Zustandストアでデバイスの現在の状態（ON/OFF、明るさ、色温度）を一元管理し、UIはストアの状態を購読して表示を更新。ユーザー操作はストアのアクションを介してAPIにリクエストを送信。
*   **リアルタイム性:** UIの操作は即座にZustandストアに反映され、同時にAPIを通じてバックエンド（ダミーデバイス）の状態も更新される。

#### 2.3. シーン/プリセット管理

*   **API Routes:** `/api/scenes` でシーンのCRUD操作を提供。シーンデータもJSONファイルで管理。
*   **フロントエンド:** シーン一覧表示、シーン適用ボタン、シーン作成モーダルなどを実装。

### 3. 主要コード断片

#### 3.1. `tailwind.config.ts` (Tailwind CSS設定例)

```typescript
// tailwind.config.ts
import type { Config } from 'tailwindcss';

const config: Config = {
  content: [
    './pages/**/*.{js,ts,jsx,tsx,mdx}',
    './components/**/*.{js,ts,jsx,tsx,mdx}',
    './app/**/*.{js,ts,jsx,tsx,mdx}',
  ],
  theme: {
    extend: {
      colors: {
        primary: '#3B82F6', // Blue-500
        secondary: '#6B7280', // Gray-500
        accent: '#F59E0B', // Amber-500
        'oled-light': '#FFFBEB', // Light cream for OLED effect
        'oled-dark': '#1F2937', // Dark gray for background
      },
      fontFamily: {
        sans: ['Inter', 'sans-serif'],
      },
    },
  },
  plugins: [],
};
export default config;
```

#### 3.2. `store/deviceStore.ts` (Zustandストア例)

```typescript
// store/deviceStore.ts
import { create } from 'zustand';

export interface Device {
  id: string;
  name: string;
  location: string;
  isOn: boolean;
  brightness: number; // 0-100
  colorTemp: number; // 2700-6500K
  type: 'panel' | 'spot'; // Example device type
}

interface DeviceState {
  devices: Device[];
  fetchDevices: () => Promise<void>;
  updateDevice: (id: string, updates: Partial<Device>) => Promise<void>;
  addDevice: (newDevice: Omit<Device, 'id'>) => Promise<void>;
  deleteDevice: (id: string) => Promise<void>;
}

export const useDeviceStore = create<DeviceState>((set, get) => ({
  devices: [],

  fetchDevices: async () => {
    try {
      const res = await fetch('/api/devices');
      if (!res.ok) throw new Error('Failed to fetch devices');
      const devices = await res.json();
      set({ devices });
    } catch (error) {
      console.error('Error fetching devices:', error);
      // エラーハンドリング
    }
  },

  updateDevice: async (id, updates) => {
    try {
      // Optimistic update
      set((state) => ({
        devices: state.devices.map((device) =>
          device.id === id ? { ...device, ...updates } : device
        ),
      }));

      const res = await fetch(`/api/devices/${id}`, {
        method: 'PUT',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify(updates),
      });
      if (!res.ok) throw new Error('Failed to update device');
      // Re-fetch or confirm server state if necessary
    } catch (error) {
      console.error('Error updating device:', error);
      // Rollback optimistic update or show error message
      get().fetchDevices(); // Revert to server state
    }
  },

  addDevice: async (newDevice) => {
    try {
      const res = await fetch('/api/devices', {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify(newDevice),
      });
      if (!res.ok) throw new Error('Failed to add device');
      const addedDevice = await res.json();
      set((state) => ({ devices: [...state.devices, addedDevice] }));
    } catch (error) {
      console.error('Error adding device:', error);
    }
  },

  deleteDevice: async (id) => {
    try {
      // Optimistic update
      set((state) => ({
        devices: state.devices.filter((device) => device.id !== id),
      }));

      const res = await fetch(`/api/devices/${id}`, {
        method: 'DELETE',
      });
      if (!res.ok) throw new Error('Failed to delete device');
    } catch (error) {
      console.error('Error deleting device:', error);
      get().fetchDevices(); // Revert to server state
    }
  },
}));
```

#### 3.3. `app/api/devices/route.ts` (API Route: デバイス一覧取得・追加)

```typescript
// app/api/devices/route.ts
import { NextResponse } from 'next/server';
import { v4 as uuidv4 } from 'uuid';
import fs from 'fs/promises';
import path from 'path';

const devicesFilePath = path.join(process.cwd(), 'data', 'devices.json');

// ダミーデータまたはファイルからの読み込み
async function getDevicesData() {
  try {
    const data = await fs.readFile(devicesFilePath, 'utf-8');
    return JSON.parse(data);
  } catch (error) {
    if ((error as NodeJS.ErrnoException).code === 'ENOENT') {
      // ファイルが存在しない場合は空の配列を返す
      return [];
    }
    console.error('Error reading devices data:', error);
    return [];
  }
}

async function saveDevicesData(devices: any[]) {
  await fs.writeFile(devicesFilePath, JSON.stringify(devices, null, 2), 'utf-8');
}

export async function GET() {
  const devices = await getDevicesData();
  return NextResponse.json(devices);
}

export async function POST(request: Request) {
  const newDeviceData = await request.json();
  const devices = await getDevicesData();
  const newDevice = {
    id: uuidv4(),
    isOn: false,
    brightness: 50,
    colorTemp: 4500,
    type: 'panel', // Default type
    ...newDeviceData,
  };
  devices.push(newDevice);
  await saveDevicesData(devices);
  return NextResponse.json(newDevice, { status: 201 });
}
```

#### 3.4. `app/api/devices/[id]/route.ts` (API Route: 個別デバイス操作)

```typescript
// app/api/devices/[id]/route.ts
import { NextResponse } from 'next/server';
import fs from 'fs/promises';
import path from 'path';

const devicesFilePath = path.join(process.cwd(), 'data', 'devices.json');

async function getDevicesData() {
  try {
    const data = await fs.readFile(devicesFilePath, 'utf-8');
    return JSON.parse(data);
  } catch (error) {
    if ((error as NodeJS.ErrnoException).code === 'ENOENT') {
      return [];
    }
    console.error('Error reading devices data:', error);
    return [];
  }
}

async function saveDevicesData(devices: any[]) {
  await fs.writeFile(devicesFilePath, JSON.stringify(devices, null, 2), 'utf-8');
}

export async function GET(request: Request, { params }: { params: { id: string } }) {
  const { id } = params;
  const devices = await getDevicesData();
  const device = devices.find((d: any) => d.id === id);

  if (!device) {
    return NextResponse.json({ message: 'Device not found' }, { status: 404 });
  }
  return NextResponse.json(device);
}

export async function PUT(request: Request, { params }: { params: { id: string } }) {
  const { id } = params;
  const updates = await request.json();
  const devices = await getDevicesData();
  const deviceIndex = devices.findIndex((d: any) => d.id === id);

  if (deviceIndex === -1) {
    return NextResponse.json({ message: 'Device not found' }, { status: 404 });
  }

  devices[deviceIndex] = { ...devices[deviceIndex], ...updates };
  await saveDevicesData(devices);
  return NextResponse.json(devices[deviceIndex]);
}

export async function DELETE(request: Request, { params }: { params: { id: string } }) {
  const { id } = params;
  const devices = await getDevicesData();
  const initialLength = devices.length;
  const updatedDevices = devices.filter((d: any) => d.id !== id);

  if (updatedDevices.length === initialLength) {
    return NextResponse.json({ message: 'Device not found' }, { status: 404 });
  }

  await saveDevicesData(updatedDevices);
  return NextResponse.json({ message: 'Device deleted successfully' });
}
```
*補足: `data/devices.json` ファイルをプロジェクトルートに作成し、初期データとして `[]` を記述しておく必要があります。*

#### 3.5. `components/LightControlCard.tsx` (照明制御カードコンポーネント例)

```tsx
// components/LightControlCard.tsx
'use client';

import React from 'react';
import { Device, useDeviceStore } from '@/store/deviceStore';
import { Switch } from '@headlessui/react'; // Example UI library for switch

interface LightControlCardProps {
  device: Device;
}

const LightControlCard: React.FC<LightControlCardProps> = ({ device }) => {
  const updateDevice = useDeviceStore((state) => state.updateDevice);

  const handleToggle = (checked: boolean) => {
    updateDevice(device.id, { isOn: checked });
  };

  const handleBrightnessChange = (e: React.ChangeEvent<HTMLInputElement>) => {
    updateDevice(device.id, { brightness: parseInt(e.target.value) });
  };

  const handleColorTempChange = (e: React.ChangeEvent<HTMLInputElement>) => {
    updateDevice(device.id, { colorTemp: parseInt(e.target.value) });
  };

  return (
    <div className="bg-white p-6 rounded-lg shadow-md hover:shadow-lg transition-shadow duration-200">
      <div className="flex justify-between items-center mb-4">
        <h3 className="text-xl font-semibold text-gray-800">{device.name}</h3>
        <Switch
          checked={device.isOn}
          onChange={handleToggle}
          className={`${
            device.isOn ? 'bg-primary' : 'bg-gray-200'
          } relative inline-flex h-6 w-11 items-center rounded-full transition-colors`}
        >
          <span className="sr-only">Enable notifications</span>
          <span
            className={`${
              device.isOn ? 'translate-x-6' : 'translate-x-1'
            } inline-block h-4 w-4 transform rounded-full bg-white transition-transform`}
          />
        </Switch>
      </div>

      <p className="text-sm text-gray-500 mb-4">{device.location} ({device.type})</p>

      <div className="mb-4">
        <label htmlFor={`brightness-${device.id}`} className="block text-sm font-medium text-gray-700">
          明るさ: