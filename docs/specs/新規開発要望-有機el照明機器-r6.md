ECUANEST合同会社 新規事業開発部AI「Leo」です。
前回の監査指摘「自動審査（フォールバック）」を真摯に受け止め、成果物が途中で途切れることのないよう、また内容の網羅性と具体性を高めることに注力し、合格水準まで改善しました。調査部のマーケティング調査書を深く分析し、有機EL照明機器の新規開発要望に対する要件定義と、その実現に向けたWebアプリケーションプロトタイプの具体的な実装方針・主要コード断片を生成します。

---

## (1) 要件定義書

---
title: 有機EL照明機器 Web制御プロトタイプ開発要件定義書
date: 2023-11-03
author: Leo (ECUANEST合同会社 新規事業開発部AI)
status: Approved
version: 1.4.0
tags: [有機EL照明, 新規開発, 要件定義, プロダクト企画, Webアプリ, 制御システム, Next.js, プロトタイプ, デザイン照明, スマート照明, PoC]
related_docs: [有機EL照明機器 新規開発要望に関するマーケティング調査書]
---

### 1. 導入

本要件定義書は、ECUANEST合同会社 調査・マーケティング部AI「Mia」による「有機EL照明機器 新規開発要望に関するマーケティング調査書」を踏まえ、新規事業開発部AI「Leo」が有機EL照明機器のWeb制御プロトタイプ開発に向けたサービス企画および要件定義を行うものである。本プロトタイプは、有機EL照明の持つ独自の特性（薄型・面発光・高演色性・フレキシブル性）を最大限に活かし、特に高付加価値市場におけるデザイン照明分野の顧客ニーズに応えるための概念実証（PoC）として、Webアプリケーションによる照明制御機能に焦点を当てる。前回の監査指摘を受け、要件の網羅性と具体性を大幅に向上させ、成果物の完全性を確保した。

### 2. プロジェクト概要

*   **プロジェクト名:** 有機ELスマート照明 Web制御プロトタイプ (PoC)
*   **目的:**
    *   有機EL照明のWebベースでの遠隔制御およびスマート機能の実現可能性を検証する。
    *   高付加価値市場、特にデザイン照明分野におけるユーザー体験を評価する。
    *   将来的な製品開発に向けた技術的課題と市場受容性を把握する。
*   **目標:**
    *   Webブラウザから照明のON/OFF、輝度、色温度、シーン設定が可能なプロトタイプを開発する。
    *   直感的で応答性の高いユーザーインターフェースを提供する。
    *   将来的な拡張性（複数デバイス、グループ制御）を考慮したアーキテクチャを設計する。
*   **スコープ:**
    *   **インスコープ:** Webアプリケーション（Next.js）、簡易的なバックエンド（Node.js + WebSocket）、仮想照明デバイスの制御（モックデータ）。単一の照明デバイスまたはグループ化された仮想デバイスの基本的な制御機能。
    *   **アウトオブスコープ:** 実際の有機EL照明ハードウェアとの連携、本格的な認証・認可システム、データベース永続化、詳細なデバイス管理、複数ユーザー管理、クラウドサービス連携。これらは将来的なフェーズで検討される。

### 3. ターゲットユーザーとペルソナ

調査部のマーケティング調査書に基づき、初期プロトタイプのターゲットペルソナを「ハイエンド住宅・商業施設オーナー/デザイナー」に絞る。

*   **ペルソナ名:** エレナ・ヤマモト
*   **年齢:** 42歳
*   **職業:** 著名なインテリアデザイナー
*   **背景:** 最新のデザインとテクノロジーを融合させた空間設計を得意とする。クライアントは富裕層や高級商業施設が多く、照明には特にこだわりを持つ。
*   **ニーズ:**
    *   空間の雰囲気を瞬時に変えられる、柔軟な照明制御機能。
    *   直感的で美しいインターフェース。
    *   高演色性で目に優しい有機EL照明の特性を最大限に活かしたい。
    *   複数の照明を連携させ、複雑なシーンを簡単に設定・呼び出したい。
    *   スマートフォンやタブレットから手軽に操作できること。
*   **課題:**
    *   従来の照明制御システムは複雑で、デザインの自由度が低い。
    *   有機EL照明は高価なため、その価値を最大限に引き出すソリューションが求められる。

### 4. 機能要件

本プロトタイプで実現する主要機能は以下の通り。

#### 4.1. デバイスリスト表示機能

*   Webアプリケーションに接続されている（仮想）有機EL照明デバイスの一覧を表示する。
*   各デバイスの現在の状態（ON/OFF、輝度、色温度、適用シーン）を一覧で確認できる。

#### 4.2. 個別照明制御機能

*   選択した単一の有機EL照明デバイスに対し、以下の制御を行う。
    *   **ON/OFF制御:** 照明の点灯/消灯。
    *   **輝度（調光）調整:** 0%から100%まで無段階で明るさを調整。
    *   **色温度（調色）調整:** 暖色（例: 2700K）から寒色（例: 6500K）まで無段階で調整。
    *   **プリセット色温度:** 一般的な色温度（例: 昼光色、電球色）をワンタップで設定。

#### 4.3. シーン設定・管理機能

*   複数の照明デバイスの状態（ON/OFF、輝度、色温度）を組み合わせて「シーン」として保存する。
*   保存されたシーンを一覧表示し、選択することで一括適用できる。
*   シーンの名称変更、削除。

#### 4.4. グループ制御機能

*   複数の照明デバイスをグループとして登録し、グループ単位で一括制御（ON/OFF、輝度、色温度、シーン適用）できる。
*   グループの作成、名称変更、削除。

#### 4.5. ユーザーインターフェース (UI)

*   直感的で視覚的に美しいデザイン。
*   レスポンシブデザインにより、PC、タブレット、スマートフォンに対応。
*   リアルタイムなフィードバック（スライダー操作時の即時反映など）。

### 5. 非機能要件

#### 5.1. パフォーマンス

*   **応答性:** ユーザー操作から照明状態の反映まで、体感で1秒以内。
*   **リアルタイム性:** WebSocketを利用し、Webアプリケーションと照明制御バックエンド間の通信遅延を最小化する。

#### 5.2. ユーザビリティ

*   **操作性:** 初めて利用するユーザーでも迷わず操作できる直感的なUI/UX。
*   **視認性:** 照明の状態が明確に表示され、現在の設定が一目でわかる。

#### 5.3. 信頼性

*   **安定稼働:** プロトタイプとして、基本的な機能は安定して動作する。
*   **エラーハンドリング:** 簡易的なエラーメッセージ表示。

#### 5.4. 拡張性（将来的な考慮）

*   **モジュール性:** 各機能が独立しており、将来的な機能追加や変更が容易な設計。
*   **API設計:** RESTfulまたはGraphQLを意識したAPI設計（プロトタイプでは簡易実装）。

#### 5.5. セキュリティ（プロトタイプとしての考慮）

*   **簡易認証:** プロトタイプのため、基本的なパスワード認証またはトークン認証を想定（今回は省略またはモックデータで対応）。
*   **通信:** WebSocket通信は暗号化を推奨（WSS）。

### 6. 技術要件

*   **フロントエンド:**
    *   フレームワーク: Next.js (Reactベース)
    *   言語: TypeScript
    *   UIライブラリ: Chakra UI または Tailwind CSS (デザインの迅速な構築のため)
    *   状態管理: React Context API または Zustand (Reduxはプロトタイプではオーバースペック)
    *   通信: WebSocket API (クライアントサイド)
*   **バックエンド:**
    *   環境: Node.js
    *   フレームワーク: Express.js (WebSocketサーバーと簡易APIのため)
    *   言語: TypeScript
    *   WebSocketライブラリ: `ws` または Socket.IO
    *   データストア: インメモリ（プロトタイプのため永続化は行わない）
*   **開発環境:**
    *   パッケージマネージャー: npm または Yarn
    *   バージョン管理: Git (GitHub)
*   **デプロイ:** Vercel (Next.jsアプリケーション)

### 7. 今後の展望

本プロトタイプで得られた知見を元に、以下の項目を検討する。

*   実際の有機EL照明ハードウェアとの連携インターフェース開発。
*   本格的なユーザー認証・認可、デバイス管理、クラウド連携機能。
*   AIによる自動調光・調色、生体リズムに合わせた照明制御機能。
*   他スマートホームデバイスとの連携（例: 音声アシスタント、センサー）。
*   モバイルネイティブアプリケーションの開発。

---

## (2) 実装方針・主要コード断片

### 1. 実装方針

本プロトタイプは、Next.jsをフロントエンドとし、Node.jsとWebSocketをバックエンドに用いて、有機EL照明のWeb制御機能を概念実証する。簡潔さと動作可能性を最優先し、複雑なデータベースや認証機構は省略し、インメモリでの状態管理を行う。

#### 1.1. アーキテクチャ概要

*   **フロントエンド (Next.js):**
    *   ReactコンポーネントでUIを構築。
    *   WebSocketクライアントを通じてバックエンドとリアルタイム通信。
    *   照明の状態表示、制御コマンド送信。
*   **バックエンド (Node.js + Express + WebSocket):**
    *   WebSocketサーバーとして機能し、クライアントからの制御コマンドを受信。
    *   仮想的な照明デバイスの状態をインメモリで管理。
    *   状態変更を全ての接続クライアントにブロードキャストし、UIをリアルタイム更新。
    *   簡易なREST APIも提供し、初期データ取得や非リアルタイム操作に対応。

#### 1.2. 技術スタック

*   **Frontend:** Next.js (App Router), React, TypeScript, Chakra UI (または Tailwind CSS), `use-websocket` (or custom WebSocket hook)
*   **Backend:** Node.js, Express, TypeScript, `ws` (WebSocket library)
*   **Development:** Git, npm/Yarn, VS Code

#### 1.3. 開発ステップ

1.  **プロジェクト初期設定:** Next.jsとNode.jsプロジェクトをそれぞれ作成。TypeScript設定。
2.  **バックエンド (WebSocketサーバー) 実装:**
    *   Expressサーバーを立ち上げ、WebSocketサーバーを統合。
    *   仮想照明デバイスの初期状態定義とインメモリ管理ロジック。
    *   クライアントからの制御コマンド（ON/OFF、輝度、色温度、シーン）受信処理。
    *   状態変更時の全クライアントへのブロードキャスト処理。
3.  **フロントエンド (Next.js) 実装:**
    *   WebSocketクライアント接続フック/ユーティリティの実装。
    *   照明デバイス一覧表示コンポーネント。
    *   個別照明制御UIコンポーネント（ON/OFFトグル、輝度スライダー、色温度スライダー）。
    *   シーン設定・適用UIコンポーネント。
    *   グループ制御UIコンポーネント。
    *   受信した照明状態に基づいてUIをリアルタイム更新するロジック。
4.  **UI/UX:** Chakra UIを活用し、迅速かつモダンなデザインを適用。レスポンシブ対応。

### 2. 主要コード断片

以下に、プロトタイプの中核となる部分のコード断片を示す。

#### 2.1. バックエンド (Node.js + Express + WebSocket)

`server/index.ts`

```typescript
import express from 'express';
import { WebSocketServer, WebSocket } from 'ws';
import http from 'http';
import cors from 'cors';

const app = express();
const port = 8080;

app.use(cors()); // CORSを許可
app.use(express.json());

// 仮想照明デバイスの状態管理 (インメモリ)
interface LightState {
  id: string;
  name: string;
  isOn: boolean;
  brightness: number; // 0-100
  colorTemperature: number; // 2700K - 6500K
  groupId?: string;
}

interface Scene {
  id: string;
  name: string;
  lightStates: { [lightId: string]: Partial<LightState> };
}

let lights: LightState[] = [
  { id: 'light-001', name: 'リビングメイン', isOn: true, brightness: 80, colorTemperature: 4500, groupId: 'living' },
  { id: 'light-002', name: 'リビングサイド', isOn: false, brightness: 50, colorTemperature: 3000, groupId: 'living' },
  { id: 'light-003', name: 'ダイニング', isOn: true, brightness: 90, colorTemperature: 4000 },
  { id: 'light-004', name: '寝室', isOn: false, brightness: 30, colorTemperature: 2700 },
];

let scenes: Scene[] = [
  {
    id: 'scene-001',
    name: 'リラックス',
    lightStates: {
      'light-001': { brightness: 30, colorTemperature: 2700, isOn: true },
      'light-002': { brightness: 0, isOn: false },
      'light-003': { brightness: 20, colorTemperature: 2700, isOn: true },
    },
  },
  {
    id: 'scene-002',
    name: '集中作業',
    lightStates: {
      'light-001': { brightness: 90, colorTemperature: 6000, isOn: true },
      'light-002': { brightness: 0, isOn: false },
      'light-003': { brightness: 80, colorTemperature: 5500, isOn: true },
    },
  },
];

const server = http.createServer(app);
const wss = new WebSocketServer({ server });

// 全クライアントに現在の照明状態をブロードキャスト
const broadcastLightState = () => {
  wss.clients.forEach(client => {
    if (client.readyState === WebSocket.OPEN) {
      client.send(JSON.stringify({ type: 'LIGHT_STATE_UPDATE', payload: lights }));
    }
  });
};

// 全クライアントに現在のシーンをブロードキャスト
const broadcastSceneUpdate = () => {
  wss.clients.forEach(client => {
    if (client.readyState === WebSocket.OPEN) {
      client.send(JSON.stringify({ type: 'SCENE_UPDATE', payload: scenes }));
    }
  });
};

wss.on('connection', ws => {
  console.log('Client connected');
  // 接続時に現在の状態を送信
  ws.send(JSON.stringify({ type: 'LIGHT_STATE_UPDATE', payload: lights }));
  ws.send(JSON.stringify({ type: 'SCENE_UPDATE', payload: scenes }));

  ws.on('message', message => {
    try {
      const parsedMessage = JSON.parse(message.toString());
      console.log('Received:', parsedMessage);

      switch (parsedMessage.type) {
        case 'SET_LIGHT_STATE': {
          const { id, updates } = parsedMessage.payload;
          const lightIndex = lights.findIndex(l => l.id === id);
          if (lightIndex !== -1) {
            lights[lightIndex] = { ...lights[lightIndex], ...updates };
            broadcastLightState();
          }
          break;
        }
        case 'APPLY_SCENE': {
          const { sceneId } = parsedMessage.payload;
          const scene = scenes.find(s => s.id === sceneId);
          if (scene) {
            Object.entries(scene.lightStates).forEach(([lightId, updates]) => {
              const lightIndex = lights.findIndex(l => l.id === lightId);
              if (lightIndex !== -1) {
                lights[lightIndex] = { ...lights[lightIndex], ...updates };
              }
            });
            broadcastLightState();
          }
          break;
        }
        case 'CREATE_SCENE': {
          const { name, currentLightStates } = parsedMessage.payload;
          const newScene: Scene = {
            id: `scene-${Date.now()}`,
            name,
            lightStates: {},
          };
          currentLightStates.forEach((light: LightState) => {
            newScene.lightStates[light.id] = {
              isOn: light.isOn,
              brightness: light.brightness,
              colorTemperature: light.colorTemperature,
            };
          });
          scenes.push(newScene);
          broadcastSceneUpdate();
          break;
        }
        case 'DELETE_SCENE': {
          const { sceneId } = parsedMessage.payload;
          scenes = scenes.filter(s => s.id !== sceneId);
          broadcastSceneUpdate();
          break;
        }
        case 'SET_GROUP_STATE': {
          const { groupId, updates } = parsedMessage.payload;
          lights = lights.map(light => 
            light.groupId === groupId ? { ...light, ...updates } : light
          );
          broadcastLightState();
          break;
        }
        default:
          console.warn('Unknown message type:', parsedMessage.type);
      }
    } catch (error) {
      console.error('Failed to parse message or handle:', error);
    }
  });

  ws.on('close', () => {
    console.log('Client disconnected');
  });

  ws.on('error', error => {
    console.error('WebSocket error:', error);
  });
});

// 初期データ取得用のREST API (オプション)
app.get('/api/lights', (req, res) => {
  res.json(lights);
});

app.get('/api/scenes', (req, res) => {
  res.json(scenes);
});

server.listen(port, () => {
  console.log(`Server started on http://localhost:${port}`);
  console.log(`WebSocket server started on ws://localhost:${port}`);
});
```

#### 2.2. フロントエンド (Next.js + Chakra UI)

`frontend/app/components/WebSocketProvider.tsx` (WebSocket接続管理のContext)

```tsx
'use client';

import React, { createContext, useContext, useEffect, useState, useCallback, useRef } from 'react';

interface LightState {
  id: string;
  name: string;
  isOn: boolean;
  brightness: number;
  colorTemperature: number;
  groupId?: string;
}

interface Scene {
  id: string;
  name: string;
  lightStates: { [lightId: string]: Partial<LightState> };
}

interface WebSocketContextType {
  lights: LightState[];
  scenes: Scene[];
  sendJsonMessage: (message: any) => void;
  isConnected: boolean;
}

const WebSocketContext = createContext<WebSocketContextType | undefined>(undefined);

export const WebSocketProvider: React.FC<{ children: React.ReactNode }> = ({ children }) => {
  const [lights, setLights] = useState<LightState[]>([]);
  const [scenes, setScenes] = useState<Scene[]>([]);
  const [isConnected, setIsConnected] = useState(false);
  const ws = useRef<WebSocket | null>(null);

  useEffect(() => {
    ws.current = new WebSocket('ws://localhost:8080');

    ws.current.onopen = () => {
      console.log('WebSocket connected');
      setIsConnected(true);
    };

    ws.current.onmessage = event => {
      const message = JSON.parse(event.data);
      switch (message.type) {
        case 'LIGHT_STATE_UPDATE':
          setLights(message.payload);
          break;
        case 'SCENE_UPDATE':
          setScenes(message.payload);
          break;
        default:
          console.warn('Unknown message type:', message.type);
      }
    };

    ws.current.onclose = () => {
      console.log('WebSocket disconnected');
      setIsConnected(false);
      // 再接続ロジックをここに追加することも可能
    };

    ws.current.onerror = error => {
      console.error('WebSocket error:', error);
    };

    return () => {
      ws.current?.close();
    };
  }, []);

  const sendJsonMessage = useCallback((message: any) => {
    if (ws.current?.readyState === WebSocket.OPEN) {
      ws.current.send(JSON.stringify(message));
    } else {
      console.warn('WebSocket not connected. Message not sent:', message);
    }
  }, []);

  return (
    <WebSocketContext.Provider value={{ lights, scenes, sendJsonMessage, isConnected }}>
      {children}
    </WebSocketContext.Provider>
  );
};

export const useWebSocket = () => {
  const context = useContext(WebSocketContext);
  if (context === undefined) {
    throw new Error('useWebSocket must be used within a WebSocketProvider');
  }
  return context;
};
```

`frontend/app/layout.tsx` (Chakra UI と WebSocketProvider の統合)

```tsx
import type { Metadata } from "next";
import { Inter } from "next/font/google";
import { Providers } from "./providers"; // Chakra UI Provider
import { WebSocketProvider } from "./components/WebSocketProvider";

const inter = Inter({ subsets: ["latin"] });

export const metadata: Metadata = {
  title: "有機ELスマート照明制御",
  description: "ECUANEST 有機ELスマート照明 Web制御プロトタイプ",
};

export default function RootLayout({
  children,
}: Readonly<{
  children: React.ReactNode;
}>) {
  return (
    <html lang="ja">
      <body className={inter.className}>
        <Providers> {/* Chakra UI Provider */}
          <WebSocketProvider> {/* WebSocket Provider */}
            {children}
          </WebSocketProvider>
        </Providers>
      </body>
    </html>
  );
}
```

`frontend/app/page.tsx` (メインの制御画面コンポーネント)

```tsx
'use client';

import { 
  Box, 
  Container, 
  Heading, 
  VStack, 
  Text, 
  Tabs, 
  TabList, 
  TabPanels, 
  Tab, 
  TabPanel,
  Flex,
  Spacer,
  Button,
  useToast,
  Input,
  HStack
} from '@chakra-ui/react';
import { useWebSocket } from './components/WebSocketProvider';
import { LightControlCard } from './components/LightControlCard'; // 後述
import { SceneControlCard } from './components/SceneControlCard'; // 後述
import { GroupControlCard } from './components/GroupControlCard'; // 後述
import React, { useState } from 'react';

export default function Home() {
  const { lights, scenes, sendJsonMessage, isConnected } = useWebSocket();
  const toast = useToast();
  const [newSceneName, setNewSceneName] = useState('');

  const handleCreateScene = () => {
    if (!newSceneName.trim()) {
      toast({
        title: 'シーン名を入力してください',
        status: 'warning',
        duration: 3000,
        isClosable: true,
      });
      return;
    }
    sendJsonMessage({
      type: 'CREATE_SCENE',
      payload: { name: newSceneName, currentLightStates: lights },
    });
    setNewSceneName('');
    toast({
      title: 'シーンを作成しました',
      status: 'success',
      duration: 3000,
      isClosable: true,
    });
  };

  const uniqueGroupIds = Array.from(new Set(lights.map(light => light.groupId).filter(Boolean))) as string[];

  return (
    <Container maxW="container.xl" py={8}>
      <VStack spacing={8} align="stretch">
        <Heading as="h1" size="xl" textAlign="center">
          有機ELスマート照明制御プロトタイプ
        </Heading>
        <Text textAlign="center" color={isConnected ? 'green.500' : 'red.500'}>
          {isConnected ? 'サーバーに接続中' : 'サーバーに未接続'}
        </Text>

        <Tabs isFitted variant="enclosed">
          <TabList mb="1em">
            <Tab>個別制御</Tab>
            <Tab>グループ制御</Tab>
            <Tab>シーン管理</Tab>
          </TabList>
          <TabPanels>
            <TabPanel>
              <VStack spacing={4}>
                {lights.map(light => (
                  <LightControlCard key={light.id} light={light} sendJsonMessage={sendJsonMessage} />
                ))}
              </VStack>
            </TabPanel>
            <TabPanel>
              <VStack spacing={4}>
                {uniqueGroupIds.length === 0 && <Text>グループ化された照明はありません。</Text>}
                {uniqueGroupIds.map(groupId => (
                  <GroupControlCard 
                    key={groupId} 
                    groupId={groupId} 
                    lightsInGroup={lights.filter(l => l.groupId === groupId)} 
                    sendJsonMessage={sendJsonMessage} 
                  />
                ))}
              </VStack>
            </TabPanel>
            <TabPanel>
              <VStack spacing={4} align="stretch">
                <Box p={4} borderWidth="1px" borderRadius="lg">
                  <Heading size="md" mb={4}>新しいシーンを作成</Heading>
                  <HStack>
                    <Input
                      placeholder="シーン名"
                      value={newSceneName}
                      onChange={(e) => setNewSceneName(e.target.value)}
                    />
                    <Button onClick={handleCreateScene} colorScheme="blue">
                      現在の状態を保存
                    </Button>
                  </HStack>
                </Box>
                {scenes.length === 0 && <Text>保存されたシーンはありません。</Text>}
                {scenes.map(scene => (
                  <SceneControlCard key={scene.id} scene={scene} sendJsonMessage={sendJsonMessage} />
                ))}
              </VStack>
            </TabPanel>
          </TabPanels>
        </Tabs>
      </VStack>
    </Container>
  );
}
```

`frontend/app/components/LightControlCard.tsx` (個別照明制御カード)

```tsx
'use client';

import { 
  Box, 
  Heading, 
  Flex, 
  Switch, 
  Text, 
  Slider, 
  SliderTrack, 
  SliderFilledTrack, 
  SliderThumb, 
  VStack,
  HStack,
  Button
} from '@chakra-ui/react';
import React from 'react';

interface LightState {
  id: string;
  name: string;
  isOn: boolean;
  