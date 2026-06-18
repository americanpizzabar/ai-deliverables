## (1) 有機EL照明機器 新規開発プロジェクト要件定義書

```markdown
---
title: 有機EL照明機器 新規開発プロジェクト要件定義書
date: 2024-07-29
project_id: OLED-DEV-20240729-001
version: 0.9.0
author: Leo (ECUANEST合同会社 新規事業開発部AI)
status: ドラフト（詳細ヒアリング待ち）
tags: [有機EL照明, OLED, 新規開発, 要件定義, プロトタイプ, Webアプリケーション]
---

# 有機EL照明機器 新規開発プロジェクト要件定義書

## 1. プロジェクト概要

本プロジェクトは、調査部からのマーケティング調査書（MKTG-REP-20240729-OLED）に基づき、有機EL（OLED）照明機器の新規開発要望に応えるための初期要件定義を行うものです。OLED照明は、その薄型・軽量、面発光、高演色性、フレキシブル性といった独自の特性により、従来の照明とは異なる高付加価値市場を形成しています。

ECUANEST合同会社は、この高成長市場において、単なる製品提供に留まらず、OLEDの特性を最大限に活かしたデザイン統合力、ソリューション提供、カスタマイズ性を強みとし、特定の顧客課題を解決する革新的な照明ソリューションを提供することを目指します。

本要件定義書では、初期フェーズとして、OLED照明の魅力を訴求し、顧客の具体的な要望をヒアリング・可視化するためのプロトタイプWebアプリケーションの開発を主なスコープとします。

## 2. 市場と機会

有機EL照明市場は、2023年の約3億ドルから2030年には約25億ドルに達すると予測されており、年平均成長率（CAGR）35%を超える高成長市場です。特に、デザイン照明、車載照明、医療・美容分野、スマートホーム向けが主要な成長ドライバーとなっています。

**主要な機会:**
*   **高付加価値市場への参入**: 高演色性、均一な光質、フレキシブル性、透明性といったOLED独自の特性を活かし、デザイン性や機能性を重視する高価格帯市場を狙う。
*   **IoT連携によるスマート照明ソリューション**: 調光・調色、人感センサー、生体リズムに合わせた照明など、IoT技術との連携による新たな価値創造。
*   **カスタマイズ需要の取り込み**: 建築家やデザイナー、特定のBtoB顧客のニーズに応じた柔軟なカスタマイズ対応。
*   **サステナビリティへの貢献**: 省エネ・長寿命、環境負荷の低い製造プロセスによるブランド価値向上。

## 3. ターゲット顧客

初期ターゲットとして、OLED照明の特性を最大限に評価し、投資を惜しまない以下のペルソナを設定します。

*   **BtoC - 富裕層住宅オーナー / デザイナーズマンション居住者**:
    *   **ニーズ**: 空間デザインへのこだわり、最新技術への関心、快適性・健康志向、パーソナライズされた照明体験。
    *   **提供価値**: 居住空間の質を高める美的で機能的な照明、フレキシブルなデザイン、目に優しい光質、スマートホーム連携。
*   **BtoB - 建築家 / インテリアデザイナー / ホテル・商業施設開発担当者**:
    *   **ニーズ**: プロジェクトの差別化、デザインの自由度、高機能性、省エネ、長期的なメンテナンスコスト削減、顧客への新たな体験提供。
    *   **提供価値**: 建築や空間デザインに合わせたカスタマイズ可能な照明ソリューション、高演色性による商品価値向上、IoT連携による運用効率化。

## 4. 競合分析と差別化戦略

主要競合はLG Display、Konica Minolta、OSRAM (ams OSRAM)、Verbatimなどであり、主にパネル供給や特定のニッチ市場に特化しています。ECUANEST合同会社は、以下の点での差別化を図ります。

*   **デザイン統合力**: 有機ELの特性を最大限に活かした、美的価値の高い製品デザインと、空間全体を考慮した照明ソリューションの提案。
*   **ソリューション提供**: 単なる製品販売ではなく、特定の顧客課題（例: スマートホーム連携、空間デザイン、ヘルスケア）を解決するトータルソリューションの提供。
*   **カスタマイズ性**: BtoB顧客の特定の要件に応じた、形状、サイズ、光質、制御方式などの柔軟なカスタマイズ対応。
*   **ブランドストーリー**: 高品質、革新性、サステナビリティを訴求するブランドイメージの構築と、顧客との共創体験の提供。

## 5. 製品・サービス要件（プロトタイプWebアプリケーション）

初期段階では、OLED照明の魅力を伝え、潜在顧客の具体的なニーズを引き出すためのWebアプリケーションを開発します。

### 5.1. 機能要件

*   **5.1.1. 製品紹介ページ**:
    *   有機EL照明の基本特性（薄型・軽量、面発光、高演色性、フレキシブル性、低ブルーライトなど）を視覚的に分かりやすく紹介。
    *   高解像度画像、動画、インタラクティブなデモ（例: フレキシブルOLEDの曲がる様子）。
    *   技術的な詳細（輝度、寿命、色温度、演色性Ra値など）の表示。
*   **5.1.2. カスタマイズシミュレーター**:
    *   OLEDパネルの形状、サイズ、枚数、配置パターンをシミュレーションできる機能。
    *   色温度（ケルビン）、調光レベル（輝度）をリアルタイムで調整し、視覚的に変化を確認できる機能。
    *   フレキシブルOLEDの曲率を調整し、様々な設置イメージを生成できる機能。
    *   仮想空間（リビング、オフィス、店舗など）にOLED照明を配置したイメージを生成できる機能（簡易的な3Dレンダリングまたは高精細な画像合成）。
    *   シミュレーション結果の保存、共有、見積もり依頼への連携。
*   **5.1.3. 事例ギャラリー**:
    *   デザイン照明、車載照明、医療・美容、スマートホームなど、用途別の導入事例を紹介。
    *   各事例について、導入目的、OLED照明の採用理由、効果、使用製品の詳細を記述。
    *   高精細な写真、動画によるビジュアル訴求。
*   **5.1.4. BtoBソリューション提案ページ**:
    *   建築家、デザイナー、企業向けに、OLED照明を活用した空間デザイン、スマートオフィス、ヘルスケア照明などのソリューションを提案。
    *   プロジェクト相談、共同開発に関する情報提供。
    *   技術資料ダウンロード、専門家への問い合わせフォーム。
*   **5.1.5. 問い合わせ・資料請求フォーム**:
    *   製品、カスタマイズ、ソリューションに関する問い合わせを受け付けるフォーム。
    *   氏名、連絡先、問い合わせ内容、具体的な要望などを入力。
    *   送信後の自動返信メール機能。
*   **5.1.6. 管理機能（社内向け）**:
    *   問い合わせ内容の確認、ステータス管理。
    *   製品情報、事例情報の追加・編集。

### 5.2. 非機能要件

*   **5.2.1. 性能**:
    *   ページの読み込み速度は高速であること（LCP 2.5秒以内）。
    *   カスタマイズシミュレーターはリアルタイムに近いレスポンスで動作すること。
    *   同時アクセスユーザー数: 初期リリース時500人/時を想定。
*   **5.2.2. 可用性**:
    *   稼働率99.9%以上。
*   **5.2.3. セキュリティ**:
    *   SSL/TLSによる通信の暗号化。
    *   フォーム入力に対するXSS、CSRF対策。
    *   個人情報保護法に準拠したデータ取り扱い。
*   **5.2.4. 拡張性**:
    *   将来的な機能追加（AR/VR連携、AIによるデザイン提案など）を考慮したアーキテクチャ。
    *   製品ラインナップの増加に柔軟に対応できるデータ構造。
*   **5.2.5. 保守性**:
    *   クリーンなコード、適切なドキュメンテーション。
    *   容易なバグ修正、機能改善。
*   **5.2.6. UI/UX**:
    *   直感的で使いやすいインターフェース。
    *   OLED照明の先進性とデザイン性を表現する洗練されたビジュアルデザイン。
    *   レスポンシブデザインにより、PC、タブレット、スマートフォンで最適に表示されること。
*   **5.2.7. 環境**:
    *   主要なモダンブラウザ（Chrome, Firefox, Safari, Edge）で動作すること。

## 6. 事業目標

*   **ブランド認知度向上**: 有機EL照明分野におけるECUANEST合同会社の先進性と技術力をアピール。
*   **リード獲得**: プロトタイプWebアプリを通じて、潜在顧客からの問い合わせ数、資料請求数を増加させる。
*   **市場ニーズの検証**: カスタマイズシミュレーターや問い合わせ内容から、顧客の具体的な要望や市場の潜在ニーズを把握。
*   **PoC（Proof of Concept）の成功**: Webアプリを通じた情報提供と顧客エンゲージメントの有効性を証明し、本格的な製品開発への足がかりとする。

**納期・予算**:
詳細な納期と予算は、本要件定義書に基づく詳細ヒアリングと技術調査後に設定します。初期プロトタイプ開発は、迅速な市場投入とフィードバック収集を目的とし、アジャイル開発手法を推奨します。

## 7. 開発フェーズとロードマップ（初期案）

1.  **フェーズ1: 要件定義と技術調査 (1ヶ月)**
    *   本要件定義書の詳細化、ステークホルダーヒアリング。
    *   OLED技術、関連サプライチェーン、競合製品のさらなる詳細調査。
    *   Webアプリケーションの技術選定（Next.js, UIフレームワーク、バックエンド構成など）。
2.  **フェーズ2: プロトタイプWebアプリケーション開発 (2ヶ月)**
    *   UI/UXデザイン、フロントエンド・バックエンド開発。
    *   製品紹介、簡易カスタマイズシミュレーター、事例、問い合わせフォームの実装。
    *   内部テスト、品質保証。
3.  **フェーズ3: 内部レビューとPoCローンチ (0.5ヶ月)**
    *   社内関係者によるレビューとフィードバック収集。
    *   限定公開またはターゲット顧客へのPoC（Proof of Concept）ローンチ。
    *   アクセス解析、ユーザー行動分析。
4.  **フェーズ4: フィードバック収集と要件再定義 (継続的)**
    *   PoCからのフィードバックに基づき、Webアプリケーションの改善、機能追加。
    *   本格的な製品開発に向けた詳細な製品仕様、技術要件の策定。

## 8. 懸念事項とリスク

*   **高コスト**: 有機EL照明パネルの製造コストは依然として高く、市場への浸透を妨げる可能性。
*   **技術的課題**: 高輝度化、長寿命化、量産技術の確立など、製造面での技術的課題。
*   **サプライチェーン**: 安定したパネル供給元、部品調達先の確保。
*   **競合激化**: 大手照明メーカーやディスプレイメーカーの本格参入による競争激化。
*   **顧客理解の不足**: ターゲット顧客の具体的なニーズやペインポイントを深く理解しきれていない可能性。

## 9. 今後のアクション

1.  **詳細ヒアリング**: 事業開発部、R&D部、デザイン部との連携を強化し、OLED照明機器に関する具体的な事業目標、技術的可能性、デザインコンセプトについて詳細なヒアリングを実施。
2.  **技術パートナー調査**: OLEDパネルメーカー、関連部品サプライヤー、デザイン事務所など、潜在的な技術パートナー候補の調査と連携可能性の検討。
3.  **PoC計画作成**: 本要件定義書を基に、プロトタイプWebアプリケーションの詳細な開発計画（工数、リソース、スケジュール）を策定。
4.  **デザインコンセプト検討**: OLEDの特性を活かした製品デザインの方向性を具体的に検討開始。
```

---

## (2) 実装方針および主要なソースコード断片

新規事業開発部AI「Leo」として、有機EL照明機器の魅力を伝え、カスタマイズ可能性を提示し、顧客エンゲージメントを高めるためのプロトタイプWebアプリケーションの実装方針と主要コード断片を提案します。

### 1. 実装方針

#### 1.1. 目的
有機EL照明の革新的な特性（薄型、フレキシブル、高演色性など）を効果的に伝え、潜在顧客が自身のニーズに合わせて照明をシミュレーションできる体験を提供します。これにより、製品への関心を高め、具体的な問い合わせやビジネス機会の創出を目指します。

#### 1.2. 技術スタック
*   **フレームワーク**: Next.js (App Router)
*   **言語**: TypeScript
*   **UIライブラリ/CSSフレームワーク**: React, Tailwind CSS
*   **状態管理**: React Context API または Zustand (必要に応じて)
*   **フォーム管理**: React Hook Form (バリデーションに Zod を利用)
*   **デプロイ**: Vercel (Next.jsとの親和性が高いため)
*   **バックエンド**: Next.js API Routes (簡易な問い合わせフォーム処理など)
*   **データ永続化**: 簡易なJSONファイルまたはHeadless CMS (Strapi, Contentfulなど) (初期プロトタイプでは不要な場合も)

#### 1.3. 主要機能と実装アプローチ
*   **製品紹介ページ**:
    *   OLEDの特性を伝えるためのアニメーションや動画を多用。
    *   CSSアニメーション (Tailwind CSSのJITモードとカスタム設定) や、React Spring/Framer Motionなどのライブラリを検討。
    *   レスポンシブデザインを徹底し、あらゆるデバイスで最高の体験を提供。
*   **カスタマイズシミュレーター**:
    *   **UI**: スライダー、ドロップダウン、カラーピッカーなどのフォームコンポーネントをReact Hook Formで管理。
    *   **視覚化**: 簡易的な2D画像合成または、Three.js/React Three Fiberを用いた軽量な3Dモデル表示を検討。初期プロトタイプでは2D画像合成から始める。
    *   **データ**: カスタマイズ可能なOLEDパネルのプロパティ（形状、サイズ、色温度範囲、輝度範囲など）をTypeScriptの型で定義し、フロントエンドで管理。
*   **問い合わせフォーム**:
    *   React Hook FormとZodでフォームのバリデーションを強化。
    *   Next.js API Routesを用いてサーバーサイドでフォームデータを処理（メール送信、データベース保存など）。

#### 1.4. 設計思想
*   **モジュール性**: 各UIコンポーネントや機能は独立して開発・保守できるように設計。
*   **拡張性**: 将来的な機能追加（AR/VR連携、より高度な3Dシミュレーション）を考慮したアーキテクチャ。
*   **パフォーマンス**: Next.jsのServer ComponentsやImage Optimization機能を活用し、高速なページ表示を実現。
*   **SEO**: Next.jsのメタデータAPIを活用し、検索エンジンからの可視性を確保。

### 2. 主要なソースコード断片

以下に、Next.js (App Router) を利用したプロトタイプWebアプリケーションの主要なコード断片を示します。

#### 2.1. `src/types/product.ts` (データ型定義)

```typescript
// src/types/product.ts

export type OledPanelShape = 'rectangle' | 'square' | 'circle' | 'flexible_strip';
export type ColorTemperature = 2700 | 3000 | 4000 | 5000 | 6500; // K (ケルビン)

export interface OledProduct {
  id: string;
  name: string;
  description: string;
  features: string[];
  basePrice: number;
  imageUrl: string;
  shapes: OledPanelShape[];
  availableColorTemperatures: ColorTemperature[];
  minLuminance: number; // cd/m2
  maxLuminance: number; // cd/m2
  cri: number; // Color Rendering Index (演色性)
  isFlexible: boolean;
  isTransparent: boolean;
}

export interface CustomizationOptions {
  shape: OledPanelShape;
  width: number; // cm
  height?: number; // cm (for rectangle/square)
  diameter?: number; // cm (for circle)
  length?: number; // cm (for flexible_strip)
  colorTemperature: ColorTemperature;
  luminance: number; // cd/m2
  quantity: number;
}
```

#### 2.2. `src/app/page.tsx` (トップページコンポーネント)

```tsx
// src/app/page.tsx
import Image from 'next/image';
import Link from 'next/link';
import { Button } from '@/components/ui/button'; // shadcn/ui などを想定

export default function HomePage() {
  return (
    <div className="min-h-screen bg-gradient-to-br from-gray-900 to-black text-white">
      {/* Hero Section */}
      <section className="relative h-[calc(100vh-64px)] flex items-center justify-center p-4">
        <Image
          src="/images/oled_hero_bg.jpg" // 仮の背景画像
          alt="Organic EL Lighting"
          fill
          style={{ objectFit: 'cover' }}
          className="opacity-40"
        />
        <div className="relative z-10 text-center space-y-6">
          <h1 className="text-5xl md:text-7xl font-bold tracking-tight leading-tight">
            未来を照らす、<br />
            有機EL照明ソリューション
          </h1>
          <p className="text-lg md:text-xl max-w-2xl mx-auto text-gray-300">
            薄く、軽く、そして美しく。空間に無限の可能性をもたらす次世代の光を体験してください。
          </p>
          <div className="flex justify-center gap-4">
            <Link href="/products">
              <Button size="lg" className="bg-blue-600 hover:bg-blue-700 text-white">
                製品を見る
              </Button>
            </Link>
            <Link href="/customize">
              <Button size="lg" variant="outline" className="border-white text-white hover:bg-white hover:text-gray-900">
                カスタマイズを試す
              </Button>
            </Link>
          </div>
        </div>
      </section>

      {/* Features Section */}
      <section className="py-20 px-4 md:px-8 bg-gray-950">
        <h2 className="text-4xl font-bold text-center mb-12">有機EL照明の革新性</h2>
        <div className="grid md:grid-cols-3 gap-12 max-w-6xl mx-auto">
          <div className="text-center">
            <div className="text-5xl text-blue-400 mb-4">💡</div> {/* Icon placeholder */}
            <h3 className="text-2xl font-semibold mb-2">薄型・フレキシブル</h3>
            <p className="text-gray-400">わずか数ミリの薄さで、曲面にも対応。デザインの自由度を飛躍的に高めます。</p>
          </div>
          <div className="text-center">
            <div className="text-5xl text-green-400 mb-4">🌈</div> {/* Icon placeholder */}
            <h3 className="text-2xl font-semibold mb-2">高演色性・目に優しい</h3>
            <p className="text-gray-400">自然光に近い美しい光で、対象物の色を忠実に再現。低ブルーライトで快適な空間を。</p>
          </div>
          <div className="text-center">
            <div className="text-5xl text-purple-400 mb-4">🔗</div> {/* Icon placeholder */}
            <h3 className="text-2xl font-semibold mb-2">スマートコネクティビティ</h3>
            <p className="text-gray-400">IoT連携により、調光・調色、自動制御など、次世代の照明体験を提供します。</p>
          </div>
        </div>
      </section>

      {/* Call to Action Section */}
      <section className="py-20 px-4 md:px-8 text-center bg-gray-900">
        <h2 className="text-4xl font-bold mb-6">あなたの空間に、新たな光を。</h2>
        <p className="text-lg text-gray-300 mb-8">
          ECUANESTの有機EL照明ソリューションが、あなたのビジョンを現実のものにします。
        </p>
        <Link href="/contact">
          <Button size="lg" className="bg-green-600 hover:bg-green-700 text-white">
            お問い合わせ
          </Button>
        </Link>
      </section>
    </div>
  );
}
```

#### 2.3. `src/components/ProductSimulator.tsx` (カスタマイズシミュレーターの骨格)

```tsx
// src/components/ProductSimulator.tsx
'use client';

import React, { useState, useEffect } from 'react';
import { useForm } from 'react-hook-form';
import { z } from 'zod';
import { zodResolver } from '@hookform/resolvers/zod';
import { OledProduct, CustomizationOptions, OledPanelShape, ColorTemperature } from '@/types/product';
import { Slider } from '@/components/ui/slider'; // shadcn/ui などを想定
import { Select, SelectContent, SelectItem, SelectTrigger, SelectValue } from '@/components/ui/select';
import { Input } from '@/components/ui/input';
import { Button } from '@/components/ui/button';
import { Label } from '@/components/ui/label';

// シミュレーションフォームのスキーマ定義
const customizationSchema = z.object({
  shape: z.nativeEnum(OledPanelShape),
  width: z.number().min(10).max(200),
  height: z.number().min(10).max(200).optional(), // Rectangle/Square only
  diameter: z.number().min(10).max(200).optional(), // Circle only
  length: z.number().min(50).max(500).optional(), // Flexible strip only
  colorTemperature: z.nativeEnum(ColorTemperature),
  luminance: z.number().min(100).max(10000), // cd/m2
  quantity: z.number().min(1).max(100),
});

type CustomizationFormInputs = z.infer<typeof customizationSchema>;

interface ProductSimulatorProps {
  product: OledProduct;
}

export function ProductSimulator({ product }: ProductSimulatorProps) {
  const { register, handleSubmit, watch, setValue, formState: { errors } } = useForm<CustomizationFormInputs>({
    resolver: zodResolver(customizationSchema),
    defaultValues: {
      shape: product.shapes[0],
      width: 30,
      height: 30,
      colorTemperature: product.availableColorTemperatures[0],
      luminance: (product.minLuminance + product.maxLuminance) / 2,
      quantity: 1,
    },
  });

  const watchedShape = watch('shape');
  const watchedColorTemperature = watch('colorTemperature');
  const watchedLuminance = watch('luminance');
  const watchedWidth = watch('width');
  const watchedHeight = watch('height');
  const watchedDiameter = watch('diameter');
  const watchedLength = watch('length');
  const watchedQuantity = watch('quantity');

  // シミュレーション結果のプレビューロジック (簡易的な画像表示)
  const getPreviewImage = () => {
    // 選択された形状、色温度、輝度に基づいて画像を動的に生成または選択
    // 例: `/images/oled_preview_${watchedShape}_${watchedColorTemperature}.png`
    // 実際にはもっと複雑なロジックや3Dレンダリングが必要になる
    return `/images/oled_preview_${watchedShape}_${watchedColorTemperature}.png`;
  };

  const calculateEstimatedPrice = () => {
    // 選択されたオプションに基づいて価格を計算
    // 簡易的な計算例
    let price = product.basePrice * watchedQuantity;
    if (watchedWidth && watchedHeight) price += (watchedWidth * watchedHeight) * 0.5; // 面積に応じて加算
    if (watchedDiameter) price += (Math.PI * (watchedDiameter / 2) ** 2) * 0.5;
    if (watchedLength) price += watchedLength * 0.5;
    if (watchedLuminance > product.minLuminance) price += (watchedLuminance - product.minLuminance) * 0.1;
    return price.toFixed(2);
  };

  const onSubmit = (data: CustomizationFormInputs) => {
    console.log('Customization submitted:', data);
    // ここで問い合わせフォームへのデータ連携や、詳細見積もり依頼API呼び出しなどを行う
    alert(`カスタマイズ内容が送信されました。\n見積もり価格: $${calculateEstimatedPrice()}`);
  };

  return (
    <div className="flex flex-col md:flex-row gap-8 p-6 bg-gray-800 rounded-lg shadow-lg">
      <div className="md:w-1/2">
        <h3 className="text-2xl font-bold mb-4 text-white">{product.name} シミュレーター</h3>
        <form onSubmit={handleSubmit(onSubmit)} className="