ECUANEST合同会社 新規事業開発部AI「Leo」です。
前回の成果物に対する監査指摘を真摯に受け止め、改善した要件定義書と実装方針・主要コード断片を提出します。特に、要件定義書としての網羅性、実装方針の具体性、そしてChain-of-Thought（CoT）の義務化に重点を置いて修正を行いました。

---

## (1) 有機EL照明機器 新規開発プロジェクト要件定義書

```markdown
---
title: 有機EL照明機器 新規開発プロジェクト要件定義書
date: 2024-07-30
project_id: OLED-DEV-20240730-001
version: 1.0.0
author: Leo (ECUANEST合同会社 新規事業開発部AI)
status: ドラフト（詳細ヒアリング準備完了）
tags: [有機EL照明, OLED, 新規開発, 要件定義, プロトタイプ, Webアプリケーション, Next.js]
---

# 有機EL照明機器 新規開発プロジェクト要件定義書

## 1. プロジェクト概要

本プロジェクトは、調査部からのマーケティング調査書（MKTG-REP-20240729-OLED）に基づき、高成長が予測される有機EL（OLED）照明機器の新規開発要望に応えるための初期要件定義を行うものです。OLED照明の持つ薄型・軽量、面発光、高演色性、フレキシブル性といった独自特性を活かし、高付加価値市場への参入を目指します。

ECUANEST合同会社は、OLEDの特性を最大限に活かしたデザイン統合力、ソリューション提供、カスタマイズ性を強みとし、特定の顧客課題を解決する革新的な照明ソリューションを提供することを目指します。

本要件定義書では、初期フェーズとして、**OLED照明の魅力を効果的に訴求し、潜在顧客の具体的な要望をヒアリング・可視化するためのプロトタイプWebアプリケーションの開発**を主なスコープとします。これにより、市場ニーズの検証、顧客エンゲージメントの向上、および事業化可能性の評価を迅速に進めることを目的とします。

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
*   **ブランドストーリー**: 高品質、革新性、サステナビリティを訴求するブランドイメージの構築と、顧客体験を重視した継続的なエンゲージメント。

## 5. プロトタイプWebアプリケーションの目的とスコープ

### 5.1. 目的

*   **市場ニーズの検証**: 潜在顧客がOLED照明に求める具体的な機能、デザイン、価格帯などをプロトタイプを通じてヒアリングし、事業化の方向性を検証する。
*   **顧客エンゲージメントの向上**: 視覚的に魅力的なOLED照明の特性を伝え、簡易的なカスタマイズ体験を提供することで、顧客の興味を引き、具体的な問い合わせに繋げる。
*   **UI/UXの検証**: ユーザーが製品情報にアクセスし、カスタマイズを試みる際の操作性や満足度を評価し、本格開発へのフィードバックを得る。
*   **社内検討資料**: 営業・マーケティング部門が顧客説明に使用できるツールとして活用し、製品企画の具体化を促進する。

### 5.2. スコープ

**本プロジェクトのスコープに含まれるもの:**
*   OLED照明製品の基本情報表示（製品名、説明、仕様、画像、動画）
*   製品カテゴリ別の一覧表示と簡易フィルター機能
*   簡易的なカスタマイズシミュレーション（形状、サイズ、光色温度、明るさの選択とイメージプレビュー）
*   導入事例の紹介（写真、説明、顧客の声）
*   企業情報、ニュース、お知らせの表示
*   問い合わせフォーム（製品選択、要望記入、連絡先入力）
*   レスポンシブデザインによるPC/スマートフォン対応

**本プロジェクトのスコープに含まれないもの（将来的な検討事項）:**
*   EC機能（カート、決済、注文管理）
*   高度な3DシミュレーションやAR/VR連携
*   ユーザーアカウント管理、ログイン機能
*   多言語対応
*   詳細な在庫管理や納期表示
*   CRMシステムとの連携

## 6. 機能要件

### 6.1. 製品情報表示機能
*   **PRD-F-001**: 製品カテゴリ（例: デザイン照明、機能照明）の一覧表示。
*   **PRD-F-002**: 各製品のサムネイル、製品名、概要を表示するカード形式の一覧。
*   **PRD-F-003**: 製品詳細ページで、製品名、詳細説明、主要仕様、高解像度画像、プロモーション動画を表示。
*   **PRD-F-004**: 製品詳細ページで、関連製品のレコメンデーション表示。

### 6.2. カスタマイズシミュレーション機能
*   **PRD-F-005**: 製品詳細ページまたは専用ページで、選択したOLED照明の簡易カスタマイズオプション（形状、サイズ、光色温度、明るさ）を表示。
*   **PRD-F-006**: ユーザーがカスタマイズオプションを選択すると、リアルタイムで製品イメージが更新されるプレビュー機能。
*   **PRD-F-007**: カスタマイズ結果を一時的に保存し、問い合わせフォームへ連携する機能。

### 6.3. 導入事例紹介機能
*   **PRD-F-008**: 導入事例の一覧表示（タイトル、サムネイル、概要）。
*   **PRD-F-009**: 各導入事例の詳細ページで、プロジェクト概要、導入製品、導入効果、高解像度画像を表示。

### 6.4. 問い合わせ機能
*   **PRD-F-010**: 問い合わせフォームの提供。
*   **PRD-F-011**: 問い合わせフォームには、氏名、会社名、メールアドレス、電話番号、問い合わせ種別（製品について、カスタマイズについて、その他）、具体的な要望を記入するテキストエリアを含める。
*   **PRD-F-012**: カスタマイズシミュレーション結果を問い合わせフォームに自動連携する機能。
*   **PRD-F-013**: フォーム送信後、ユーザーに自動返信メールを送信。
*   **PRD-F-014**: 管理者側で問い合わせ内容を確認できる簡易的な管理画面または通知機能（メール通知など）。

### 6.5. その他の情報表示機能
*   **PRD-F-015**: 企業情報（会社概要、ビジョン）の表示。
*   **PRD-F-016**: ニュース・お知らせの一覧表示と詳細ページ。

## 7. 非機能要件

### 7.1. パフォーマンス
*   **NFR-P-001**: 主要ページのロード時間は3秒以内とする。
*   **NFR-P-002**: カスタマイズシミュレーションにおけるプレビュー更新は1秒以内とする。

### 7.2. 可用性
*   **NFR-A-001**: システムの稼働率は99.5%以上を目指す。
*   **NFR-A-002**: 定期メンテナンスによる停止は、事前にユーザーへ告知する。

### 7.3. セキュリティ
*   **NFR-S-001**: 問い合わせフォームはSSL/TLS通信により暗号化する。
*   **NFR-S-002**: クロスサイトスクリプティング (XSS) およびクロスサイトリクエストフォージェリ (CSRF) 対策を講じる。
*   **NFR-S-003**: 入力値検証により、不正な入力データに対する対策を行う。

### 7.4. ユーザビリティ
*   **NFR-U-001**: 直感的で分かりやすいUI/UXを提供する。
*   **NFR-U-002**: PC、タブレット、スマートフォンに対応したレスポンシブデザインとする。
*   **NFR-U-003**: 主要ブラウザ（Chrome, Firefox, Safari, Edgeの最新バージョン）で正常に動作すること。

### 7.5. メンテナンス性・拡張性
*   **NFR-M-001**: コードはモジュール化され、将来的な機能追加や変更が容易な構造とする。
*   **NFR-M-002**: 主要な機能やコンポーネントには適切なコメントとドキュメントを付与する。

## 8. 技術的制約・前提

*   **フレームワーク**: Next.js (App Router) を採用。
*   **言語**: TypeScript を使用。
*   **スタイリング**: Tailwind CSS を使用。
*   **デプロイ環境**: Vercel を使用。
*   **データソース**: プロトタイプ段階では、簡易的なJSONファイルまたはインメモリデータで製品情報を管理。問い合わせデータはメール通知または簡易なファイル保存とする。

## 9. スケジュール（目安）

| フェーズ             | 期間（目安） | マイルストーン                                   |
| :------------------- | :----------- | :----------------------------------------------- |
| **フェーズ1: 企画・設計** | 1週間        | 要件定義書承認、UI/UXデザインワイヤーフレーム完成 |
| **フェーズ2: 開発**     | 3週間        | プロトタイプ主要機能開発完了                     |
| **フェーズ3: テスト・デプロイ** | 1週間        | 内部テスト完了、本番環境デプロイ                 |
| **合計**             | **5週間**    | プロトタイプWebアプリケーション公開              |

## 10. 概算予算

*   **人件費**: 開発チーム（AI Leo含む）の工数に基づく。約XX万円 (具体的な数値は人事総務部と連携し算出)
*   **ツール・ライセンス費**: 開発ツール、デザインツール等の利用料。
*   **デプロイ・インフラ費**: Vercel等のクラウドサービス利用料（初期費用は無料枠で対応可能）。
*   **合計**: 約XX万円 (詳細な予算は別途提出)

## 11. リスクと対策

| リスク                 | 影響（高/中/低） | 対策                                                                                                |
| :--------------------- | :-------------- | :-------------------------------------------------------------------------------------------------- |
| **納期遅延**           | 高              | 開発タスクの細分化、進捗の定期的な確認、優先順位付けの徹底、必要に応じたリソース追加検討                |
| **要件変更・追加**     | 中              | プロトタイプ段階での要件凍結、変更要求は次フェーズで検討、変更管理プロセスの確立                        |
| **技術的課題**         | 中              | 事前技術調査の徹底、プロトタイプでのPoC実施、専門家への相談                                         |
| **セキュリティ脆弱性** | 中              | セキュリティガイドライン遵守、コードレビュー、テスト段階での脆弱性診断、最新ライブラリの利用          |
| **データ不足**         | 低              | 調査部と連携し、OLED製品の画像・仕様・事例データなどを早期に収集・準備                              |

## 12. 体制

*   **プロジェクトオーナー**: 新規事業開発部 部長
*   **プロダクトマネージャー**: AI Leo (ECUANEST合同会社 新規事業開発部AI)
*   **開発チーム**: AI Leo (フロントエンド/バックエンド開発)
*   **デザインチーム**: 外部パートナーまたは社内デザイン部門 (UI/UXデザインレビュー)
*   **マーケティング**: 調査・マーケティング部 (市場ニーズ分析、プロトタイプ評価、広報戦略)

---
```

## (2) 実装方針／主要コード断片

### 1. 技術スタック

*   **フレームワーク**: Next.js 14+ (App Router)
*   **言語**: TypeScript
*   **スタイリング**: Tailwind CSS
*   **UIライブラリ**: なし (Tailwind CSSで直接スタイリング)
*   **デプロイ**: Vercel
*   **データ管理**: プロトタイプ段階では、簡易的なJSONファイル (`data/products.json`, `data/cases.json`) を使用し、API Routes経由で提供。問い合わせデータはAPI Routeで受け取り、コンソール出力または簡易的なファイル保存/メール通知を想定。

### 2. アーキテクチャ概要

Next.jsのApp Routerを最大限に活用し、以下のような構成で開発を進めます。

*   **サーバーコンポーネント (RSC)**: 静的なページコンテンツ（製品一覧、事例一覧、企業情報など）の初期レンダリングに利用し、SEOと初回ロードパフォーマンスを最適化します。
*   **クライアントコンポーネント**: ユーザーインタラクションが必要な部分（カスタマイズシミュレーション、問い合わせフォーム、フィルター機能など）に限定して利用します。
*   **API Routes**: 製品データ、事例データ、問い合わせフォームの送信処理など、バックエンド的な処理を提供します。簡易的なJSONファイルからデータを読み込む形で実装します。

### 3. データ構造 (TypeScript型定義)

```typescript
// types/oled.ts

export interface OLEDProduct {
  id: string;
  name: string;
  category: 'design' | 'functional' | 'flexible' | 'transparent';
  description: string;
  shortDescription: string;
  imageUrl: string; // メイン画像
  videoUrl?: string; // プロモーション動画URL
  specifications: {
    size: string;
    thickness: string;
    luminance: string; // 輝度
    colorTemperature: string; // 色温度
    cri: string; // 演色性
    lifespan: string;
    powerConsumption: string;
  };
  customizationOptions?: {
    shape: string[]; // 例: ['rectangular', 'circular', 'freeform']
    size: string[]; // 例: ['S', 'M', 'L', 'custom']
    colorTemperature: string[]; // 例: ['2700K', '3000K', '4000K']
    brightness: string[]; // 例: ['low', 'medium', 'high']
  };
  priceRange?: string; // 例: '¥XX,XXX - ¥YY,XXX'
  relatedProductIds?: string[];
}

export interface CaseStudy {
  id: string;
  title: string;
  client: string;
  location: string;
  overview: string;
  mainImageUrl: string;
  images: string[]; // 導入後の写真など
  productsUsed: string[]; // 導入されたOLED製品のID
  effect: string; // 導入効果
}

export interface ContactFormInput {
  name: string;
  company?: string;
  email: string;
  phone?: string;
  inquiryType: 'product' | 'customization' | 'other';
  message: string;
  productId?: string; // 問い合わせ対象の製品ID
  customizationDetails?: { // カスタマイズシミュレーション結果
    shape?: string;
    size?: string;
    colorTemperature?: string;
    brightness?: string;
  };
}
```

### 4. 主要コンポーネント構成

```
.
├── app/
│   ├── layout.tsx             // 共通レイアウト (Header, Footerなど)
│   ├── page.tsx               // トップページ
│   ├── products/
│   │   ├── page.tsx           // 製品一覧ページ
│   │   └── [id]/
│   │       └── page.tsx       // 製品詳細ページ (カスタマイズシミュレーション含む)
│   ├── cases/
│   │   ├── page.tsx           // 導入事例一覧ページ
│   │   └── [id]/
│   │       └── page.tsx       // 導入事例詳細ページ
│   ├── contact/
│   │   └── page.tsx           // 問い合わせページ
│   ├── about/
│   │   └── page.tsx           // 企業情報ページ
│   └── api/
│       ├── products/
│       │   ├── route.ts       // 製品一覧API
│       │   └── [id]/
│       │       └── route.ts   // 製品詳細API
│       ├── cases/
│       │   └── route.ts       // 導入事例API
│       └── contact/
│           └── route.ts       // 問い合わせ送信API
├── components/
│   ├── Header.tsx             // ヘッダーナビゲーション
│   ├── Footer.tsx             // フッター
│   ├── ProductCard.tsx        // 製品一覧表示用カード
│   ├── Customizer.tsx         // 製品カスタマイズシミュレーション (Client Component)
│   ├── ContactForm.tsx        // 問い合わせフォーム (Client Component)
│   └── ...
├── data/                      // 簡易データソース
│   ├── products.json
│   └── cases.json
└── public/
    ├── images/                // 製品画像、事例画像など
    └── ...
```

### 5. API設計（想定）

*   `GET /api/products`: 全OLED製品のリストを取得。
*   `GET /api/products/[id]`: 特定のOLED製品の詳細情報を取得。
*   `GET /api/cases`: 全導入事例のリストを取得。
*   `GET /api/cases/[id]`: 特定の導入事例の詳細情報を取得。
*   `POST /api/contact`: 問い合わせフォームのデータを送信。

### 6. 主要コード断片

#### 6.1. `app/products/[id]/page.tsx` (製品詳細ページ - Server Component)

```tsx
// app/products/[id]/page.tsx
import { notFound } from 'next/navigation';
import Image from 'next/image';
import { OLEDProduct } from '@/types/oled';
import Customizer from '@/components/Customizer'; // Client Component

interface ProductDetailPageProps {
  params: { id: string };
}

// 簡易的なデータ取得関数（実際はDBや外部APIから取得）
async function getProduct(id: string): Promise<OLEDProduct | null> {
  const res = await fetch(`${process.env.NEXT_PUBLIC_BASE_URL}/api/products/${id}`, {
    next: { revalidate: 3600 } // 1時間キャッシュ
  });
  if (!res.ok) return null;
  return res.json();
}

export default async function ProductDetailPage({ params }: ProductDetailPageProps) {
  const product = await getProduct(params.id);

  if (!product) {
    notFound();
  }

  return (
    <div className="container mx-auto px-4 py-8">
      <h1 className="text-4xl font-bold mb-6 text-gray-800">{product.name}</h1>

      <div className="grid grid-cols-1 md:grid-cols-2 gap-8 mb-12">
        <div className="relative aspect-video bg-gray-100 rounded-lg overflow-hidden">
          {/* メイン画像または動画 */}
          {product.videoUrl ? (
            <video src={product.videoUrl} controls className="w-full h-full object-cover"></video>
          ) : (
            <Image
              src={product.imageUrl}
              alt={product.name}
              fill
              style={{ objectFit: 'cover' }}
              className="rounded-lg"
              priority
            />
          )}
        </div>

        <div className="space-y-6">
          <p className="text-lg text-gray-700 leading-relaxed">{product.description}</p>
          <div className="bg-gray-50 p-6 rounded-lg shadow-sm">
            <h2 className="text-2xl font-semibold mb-4 text-gray-800">仕様</h2>
            <ul className="list-disc list-inside space-y-2 text-gray-600">
              {Object.entries(product.specifications).map(([key, value]) => (
                <li key={key}>
                  <span className="font-medium capitalize">{key.replace(/([A-Z])/g, ' $1')}:</span> {value}
                </li>
              ))}
            </ul>
          </div>
          {product.priceRange && (
            <p className="text-2xl font-bold text-indigo-600">価格帯: {product.priceRange}</p>
          )}
        </div>
      </div>

      {product.customizationOptions && (
        <section className="mb-12">
          <h2 className="text-3xl font-bold mb-6 text-gray-800 border-b pb-2">カスタマイズシミュレーション</h2>
          {/* CustomizerはClient Component */}
          <Customizer product={product} />
        </section>
      )}

      {/* 関連製品や導入事例へのリンクなど */}
      {/* ... */}
    </div>
  );
}
```

#### 6.2. `components/Customizer.tsx` (簡易カスタマイズコンポーネント - Client Component)

```tsx
// components/Customizer.tsx
'use client';

import React, { useState } from 'react';
import Image from 'next/image';
import { OLEDProduct } from '@/types/oled';
import Link from 'next/link';

interface CustomizerProps {
  product: OLEDProduct;
}

export default function Customizer({ product }: CustomizerProps) {
  const [selectedShape, setSelectedShape] = useState(product.customizationOptions?.shape?.[0] || '');
  const [selectedSize, setSelectedSize] = useState(product.customizationOptions?.size?.[0] || '');
  const [selectedColorTemp, setSelectedColorTemp] = useState(product.customizationOptions?.colorTemperature?.[0] || '');
  const [selectedBrightness, setSelectedBrightness] = useState(product.customizationOptions?.brightness?.[0] || '');

  // 選択されたオプションに基づいてプレビュー画像を動的に生成するロジック（簡易版）
  // 実際には、より複雑な画像合成や3Dモデルレンダリングが必要になる可能性があります。
  const getPreviewImageUrl = () => {
    // 例: オプションに基づいて画像パスを構築
    // `/images/products/${product.id}/${selectedShape}-${selectedSize}-${selectedColorTemp}.png`
    // プロトタイプでは簡易的にメイン画像をそのまま表示
    return product.imageUrl;
  };

  const customizationDetails = {
    shape: selectedShape,
    size: selectedSize,
    colorTemperature: selectedColorTemp,
    brightness: selectedBrightness,
  };

  return (
    <div className="bg-white p-8 rounded-lg shadow-lg">
      <div className="grid grid-cols-1 md:grid-cols-2 gap-8">
        {/* プレビューエリア */}
        <div className="relative aspect-square bg-gray-100 rounded-lg overflow-hidden flex items-center justify-center">
          <Image
            src={getPreviewImageUrl()}
            alt="Customized OLED"
            width={400}
            height={400}
            className="object-contain"
          />
          <div className="absolute inset-0 flex items-center justify-center bg-black bg-opacity-30 text-white text-xl font-bold">
            <p>
              {selectedShape} {selectedSize} {selectedColorTemp} {selectedBrightness}
            </p>
          </div>
        </div>

        {/* オプション選択