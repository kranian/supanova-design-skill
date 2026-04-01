# 철목수 랜딩 페이지 기획서 v2

> 버전: 2.0
> 작성일: 2026-04-01
> 프로젝트: 철목수(Cheolmoksu) 스틸하우스 전문 시공사 랜딩 페이지
> 근거: [경쟁력 분석](./kateye-analysis-cheolmoksu-20260401-001.md) + [디자인 리서치](./research/README.md) + [기획 리뷰](./research/planning-review.md)

---

## 1. 프로젝트 요약

### 1.1 목표

유튜브 채널 @철목수의 트래픽을 웹사이트로 전환하여, **전화 상담 및 견적 문의**를 극대화하는 프리미엄 랜딩 페이지를 구축합니다.

### 1.2 타겟 고객

| 세그먼트 | 니즈 | 전환 경로 |
|---------|------|----------|
| 스틸하우스 신축 희망자 | 믿을 수 있는 시공사 탐색 | 유튜브 → 랜딩 → 전화/견적 |
| 커스텀 철제 수요자 | 가성비 좋은 직영 공장 | 검색 → 랜딩 → 전화/카카오 |
| 건축 정보 탐색자 | 스틸하우스 정보 수집 | 유튜브/검색 → 랜딩 → 구독/북마크 |

### 1.3 핵심 성과 지표

| KPI | 목표 | 업계 평균 |
|-----|------|----------|
| 전환율 | 5%+ | 1.9% |
| LCP | 2.5초 이내 | - |
| 모바일 전환 | 3%+ | - |
| 바운스율 | 40% 이하 | - |
| 첫 로드 | 800KB 이내 | - |

---

## 2. 브랜드 아이덴티티

### 2.1 브랜드 에센스

```
"철을 다루는 장인, 당신의 집을 짓습니다"
```

**브랜드 키워드**: 장인정신, 투명성, 엔지니어링 품질, 직영 공장, 신뢰

### 2.2 톤 앤 매너

- **차분한 자신감**: 과장 없이 결과로 말하는 톤
- **기술적 권위**: 구조 계산, 도면, 공정 등 전문용어 자연스럽게 사용
- **따뜻한 장인**: 차가운 기술이 아닌 "사람의 집을 짓는" 감성
- **투명함**: 가격, 공정, 시간 — 숨기지 않는 태도

---

## 3. 디자인 시스템

### 3.1 컬러 팔레트 — Steel Authority

| 역할 | 색상 | HEX | 용도 |
|------|------|-----|------|
| Primary | Warm Black | `#1C1B1A` | 배경, 헤더, 푸터 |
| Accent | Champagne Gold | `#B08D57` | CTA 버튼, 강조, 호버 |
| Light Accent | Bright Gold | `#d9b061` | 아이콘 하이라이트, 수치 강조 |
| Background | Warm Cream | `#F2EFEA` | 밝은 섹션 배경 |
| Text Light | White | `#FFFFFF` | 다크 배경 위 텍스트 |
| Text Dark | Warm Black | `#1C1B1A` | 밝은 배경 위 텍스트 |
| Text Muted | Gray | `#6B7280` | 보조 텍스트, 캡션 |
| Border | Light Gray | `#E5E7EB` | 카드 테두리, 구분선 |

**패턴**: 다크 섹션(S1 히어로, S5 시공과정, S9 연락처, Footer)과 라이트 섹션(S2~S4, S6~S8)을 교차 배치하여 리듬감 부여.

### 3.2 타이포그래피

```css
/* 한글 */
--font-heading-kr: 'Noto Serif KR', serif;        /* 헤드라인: 권위+장인 */
--font-body-kr: 'Pretendard', sans-serif;          /* 본문: 가독성+현대 */

/* 영문 */
--font-heading-en: 'Cormorant Garamond', serif;    /* 헤드라인: 전통+품격 */
--font-body-en: 'Inter', sans-serif;               /* 본문: 스크린최적화 */

/* 타입 스케일 (8px base) */
--text-display: 72px / 1.1;     /* 히어로 메인 카피 */
--text-h1: 48px / 1.17;         /* 섹션 타이틀 */
--text-h2: 36px / 1.22;         /* 서브 타이틀 */
--text-h3: 24px / 1.33;         /* 카드 타이틀 */
--text-body: 16px / 1.75;       /* 본문 (한글 최적화) */
--text-small: 14px / 1.43;      /* 캡션, 부가 정보 */
--text-xs: 12px / 1.5;          /* 법적 고지, 주석 */

/* 모바일 스케일 */
--text-display-mobile: 40px / 1.15;
--text-h1-mobile: 32px / 1.2;
--text-h2-mobile: 24px / 1.25;
```

**폰트 로딩 전략**:
- Pretendard: CDN 동적 서브셋 (cdn.jsdelivr.net)
- Noto Serif KR: Google Fonts (wght@700;900)
- Cormorant Garamond: Google Fonts (wght@600;700)
- Inter: Google Fonts (wght@400;500;600)
- `font-display: swap` 필수

### 3.3 레이아웃 시스템

```css
/* 컨테이너 */
--container-max: 1200px;        /* 전체 콘텐츠 최대 폭 */
--container-text: 720px;        /* 텍스트 최대 폭 */
--container-padding: 24px;      /* 모바일 좌우 여백 */

/* 섹션 스페이싱 */
--section-padding-y: 96px;      /* 데스크톱 섹션 상하 여백 */
--section-padding-y-mobile: 64px;

/* 8px 그리드 */
--space-1: 8px;
--space-2: 16px;
--space-3: 24px;
--space-4: 32px;
--space-6: 48px;
--space-8: 64px;
--space-12: 96px;
--space-16: 128px;

/* 브레이크포인트 */
--bp-sm: 640px;
--bp-md: 768px;
--bp-lg: 1024px;
--bp-xl: 1280px;
```

### 3.4 컴포넌트 스타일

```css
/* 버튼 — Primary CTA */
.btn-primary {
  background: #B08D57;
  color: #FFFFFF;
  padding: 16px 32px;
  border-radius: 4px;
  font-weight: 600;
  font-size: 16px;
  min-height: 48px;              /* 터치 타겟 */
  transition: background 0.2s;
}
.btn-primary:hover {
  background: #9A7A4A;
}

/* 버튼 — Ghost/Secondary */
.btn-ghost {
  border: 1px solid #FFFFFF;
  color: #FFFFFF;
  padding: 16px 32px;
  border-radius: 4px;
  background: transparent;
}

/* 카드 */
.card {
  background: #FFFFFF;
  border: 1px solid #E5E7EB;
  border-radius: 8px;
  padding: 32px;
  box-shadow: 0 1px 3px rgba(0,0,0,0.05);
}

/* 카드 호버 */
.card:hover {
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
  transform: translateY(-2px);
  transition: all 0.3s ease;
}
```

---

## 4. 페이지 구조 상세

### 4.1 내비게이션

```
[로고: 철목수]  서비스  포트폴리오  시공과정  후기  문의  ☎ 010-411-5210  [무료 상담]
```

- 스크롤 시 배경 블러 효과 (`backdrop-filter: blur(12px)`)
- 모바일: 햄버거 메뉴 + 전화번호 상시 노출
- `position: sticky; top: 0; z-index: 50;`
- 스크롤 다운 시 축소 (py: 24px → 16px)

### 4.2 S1: 히어로 섹션

**레이아웃**: 풀스크린 (100vh)

```
배경: 비디오 루프 (15-30초, 스틸하우스 시공 타임랩스)
      + 다크 오버레이 (linear-gradient, 50% opacity)
      + 폴백: 완공 사진 (정적 이미지)

메인 카피:
  "철을 다루는 장인,
   당신의 집을 짓습니다"
  (Noto Serif KR, 72px, #FFFFFF)

서브 카피:
  "스틸하우스 전문 시공 | 커스텀 철제 제작 | 직영 공장 운영"
  (Pretendard, 18px, rgba(255,255,255,0.8))

CTA 그룹:
  [무료 견적 받기]     — Primary (Champagne Gold)
  [시공 사례 보기]     — Ghost (White Border)

하단 스크롤 인디케이터:
  ↓ (애니메이션 bounce)
```

**애니메이션**: GSAP으로 텍스트 순차 페이드인 (0.3초 간격)

### 4.3 S2: 신뢰 지표

**레이아웃**: 4-column (모바일 2x2 그리드)
**배경**: Warm Cream (#F2EFEA)

```
┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐
│    XX    │  │    XX    │  │    XX    │  │    ✓     │
│  시공 실적  │  │   경력    │  │  고객만족도 │  │  직영 공장  │
│    동     │  │    년     │  │    %     │  │   운영    │
└──────────┘  └──────────┘  └──────────┘  └──────────┘
```

**애니메이션**: Intersection Observer 트리거 → 카운트업 (0에서 목표값까지 2초)

### 4.4 S3: 서비스

**레이아웃**: 2-column 균등 분할 (모바일 스택)
**배경**: White

```
좌측 카드 — 스틸하우스 (프리미엄)
  이미지: 완공된 스틸하우스 외관
  타이틀: "스틸하우스 신축"
  설명: "기초부터 완공까지, 구조 계산부터 마감 디테일까지
        엔지니어링 품질로 완성하는 프리미엄 철골조주택"
  포인트: 구조 안전성 / 내구성 50년+ / 맞춤 설계 / 에너지 효율
  [스틸하우스 상담하기]

우측 카드 — 커스텀 철제 제작 (가격경쟁력)
  이미지: 제작 중인 철제 계단/가대
  타이틀: "커스텀 철제 제작"
  설명: "직영 공장에서 직접 제작하여 중간 마진 없이
        합리적인 가격으로 제공하는 맞춤 철제 솔루션"
  포인트: 가대 / 계단 / 펜스 / 철제가구 / 시중대비 20-40% 절감
  [견적 문의하기]
```

**효과**: 카드 호버 시 이미지 줌 (scale 1.05) + 그림자 확대

### 4.5 S4: 포트폴리오

**레이아웃**: 탭 필터 + 매서너리 그리드
**배경**: Warm Cream (#F2EFEA)

```
탭: [전체] [스틸하우스] [커스텀 제작]

대표 프로젝트 — Before/After 슬라이더 (풀폭)
  드래그 핸들로 시공 전/후 비교
  라벨: "시공 전" ←→ "시공 후"
  하단: 프로젝트명 | 위치 | 규모 | 시공 기간

프로젝트 그리드 (3-column, 모바일 1-column)
  각 카드:
  ┌──────────────────┐
  │  [프로젝트 사진]    │
  │                    │
  ├──────────────────┤
  │  프로젝트명         │
  │  위치 | 규모        │
  └──────────────────┘
  호버: 오버레이 + "자세히 보기" 텍스트
```

### 4.6 S5: 시공 과정

**레이아웃**: 세로 타임라인 (데스크톱: 좌우 교차, 모바일: 단일 열)
**배경**: Warm Black (#1C1B1A) — 다크 섹션

```
섹션 타이틀: "투명한 시공 과정" (#FFFFFF)
부제: "모든 공정을 유튜브로 공개합니다" (rgba(255,255,255,0.7))

타임라인:
  ● 01 상담 & 현장 답사 ─── [설명] ─── [YouTube 썸네일]
  ● 02 설계 & 구조 계산 ─── [설명] ─── [YouTube 썸네일]
  ● 03 인허가 ─────────── [설명]
  ● 04 기초 공사 ────────── [설명] ─── [YouTube 썸네일]
  ● 05 철골 조립 ────────── [설명] ─── [YouTube 썸네일]
  ● 06 외장 마감 ────────── [설명] ─── [YouTube 썸네일]
  ● 07 내장 마감 ────────── [설명] ─── [YouTube 썸네일]
  ● 08 완공 & 입주 ────── [설명] ─── [YouTube 썸네일]

YouTube 임베드: lite-youtube-embed (224배 빠른 로딩)
하단 CTA: [유튜브 채널 구독하기] (Ghost, Red accent)
```

**애니메이션**: GSAP ScrollTrigger로 각 단계 순차 등장

### 4.7 S6: 차별화 포인트

**레이아웃**: 3-column 아이콘 카드 (모바일 스택)
**배경**: White

```
┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐
│    [공장 아이콘]   │  │  [유튜브 아이콘]   │  │  [설계 아이콘]    │
│                   │  │                   │  │                  │
│  직영 공장 운영    │  │  투명한 시공 공개   │  │  엔지니어링 품질  │
│                   │  │                   │  │                  │
│  중간 마진 없는     │  │  유튜브 채널로      │  │  구조 계산부터     │
│  합리적 가격.      │  │  시공 전 과정을     │  │  마감까지         │
│  직영 공장에서      │  │  100% 공개.        │  │  직접 관리.       │
│  직접 제작합니다.   │  │  숨기지 않습니다.   │  │  품질에 타협      │
│                   │  │                   │  │  없습니다.        │
└─────────────────┘  └─────────────────┘  └─────────────────┘
```

**아이콘**: Lucide — `factory`, `youtube`, `drafting-compass`

### 4.8 S7: 고객 후기

**레이아웃**: 캐러셀 (3장 보이기, 모바일 1장)
**배경**: Warm Cream (#F2EFEA)

```
섹션 타이틀: "고객 후기"

후기 카드:
┌──────────────────────────────┐
│  [시공 완료 사진]              │
├──────────────────────────────┤
│  ★★★★★                       │
│  "처음에는 유튜브에서 보고..."    │
│  "직접 방문하니 영상 그대로..."   │
│                              │
│  홍길동님 | 경기도 | 스틸하우스   │
└──────────────────────────────┘

← [이전]  ● ● ● ○ ○  [다음] →

하단 CTA: [무료 상담 받기] (Primary — Champagne Gold)
         (CTA 인접 배치: 270% 전환 증가)
```

### 4.9 S8: FAQ

**레이아웃**: 아코디언 (최대폭 720px, 중앙 정렬)
**배경**: White

```
Q. 스틸하우스 시공 비용은 얼마인가요?
   ▼ 평당 기준 금액은 설계, 마감재, 부지 조건에 따라 달라집니다.
     무료 상담을 통해 정확한 견적을 받아보세요.

Q. 시공 기간은 얼마나 걸리나요?
   ▼ 일반적으로 30~40평 기준 3~4개월 소요됩니다.
     설계 및 인허가 기간은 별도입니다.

Q. 원하는 설계로 맞춤 시공이 가능한가요?
   ▼ 네, 고객님의 요구사항을 반영한 100% 맞춤 설계가 가능합니다.

Q. 하자 보증은 어떻게 되나요?
   ▼ 건축법에 따른 하자 보증 기간을 준수하며,
     시공 후에도 A/S를 지원합니다.

Q. 커스텀 철제 제작 최소 주문량은?
   ▼ 1개부터 제작 가능합니다. 직영 공장이라 소량도 환영합니다.

Q. 시공 가능 지역은 어디인가요?
   ▼ 전국 시공 가능하며, 지역에 따라 출장비가 발생할 수 있습니다.
```

**SEO**: FAQ 섹션은 `<script type="application/ld+json">` FAQPage 구조화 데이터 적용.

### 4.10 S9: 연락처 & 최종 CTA

**레이아웃**: 2-column (모바일 스택)
**배경**: Warm Black (#1C1B1A) — 다크 섹션

```
좌측 — 견적 폼 (멀티스텝)

  "무료 견적 상담"
  "24시간 내 연락드리겠습니다"

  Step 1 of 2 ━━━━━━━━━━━━━━━━━░░░░░░░░░░░░░░░

  이름        [                    ]
  연락처      [                    ]
  건축 희망 지역 [                    ]

  [다음 단계 →]

  ---

  Step 2 of 2 ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  희망 평수      [드롭다운 ▼]
  예산 범위      [드롭다운 ▼]
  희망 연락 방법  ○ 전화  ○ 카카오톡  ○ 둘 다

  [견적 요청하기]

우측 — 연락 정보

  ☎ 전화 상담
  010-411-5210
  (평일 09:00 - 18:00)

  💬 카카오톡 상담
  @철목수
  [카카오톡으로 상담하기]

  📺 유튜브
  @철목수
  [채널 바로가기]

  📍 오시는 길
  [네이버 지도 임베드]
```

### 4.11 Footer

```
[로고: 철목수]

스틸하우스 전문 시공 | 커스텀 철제 제작

유튜브  인스타그램  네이버블로그

────────────────────────────────────
상호: 철목수 | 대표: OOO
사업자등록번호: XXX-XX-XXXXX
주소: XXXXXXXX
전화: 010-411-5210

Copyright 2026 철목수. All rights reserved.
```

### 4.12 모바일 스티키 바

```
고정 위치: bottom 0 (모바일만, md 이상에서 hidden)
높이: 64px
배경: #1C1B1A (90% opacity, backdrop-blur)

┌──────────────┬──────────────┬──────────────┐
│  ☎ 전화 상담  │  💬 카카오톡  │  📋 견적 문의  │
└──────────────┴──────────────┴──────────────┘

전화: tel:010-411-5210 (바로 연결)
카카오: 카카오톡 채널 링크
견적: S9 섹션으로 스크롤
```

---

## 5. 기술 스택

### 5.1 프론트엔드

| 항목 | 선택 | CDN/소스 |
|------|------|---------|
| 마크업 | HTML5 시맨틱 | - |
| 스타일 | Tailwind CSS 3.x | cdn.tailwindcss.com |
| 애니메이션 | GSAP + ScrollTrigger | cdnjs.cloudflare.com/ajax/libs/gsap |
| 스무스 스크롤 | Lenis | cdn.jsdelivr.net/npm/lenis |
| YouTube | lite-youtube-embed | cdn.jsdelivr.net/npm/lite-youtube-embed |
| 아이콘 | Lucide | unpkg.com/lucide |

### 5.2 폰트 CDN

```html
<!-- Pretendard (동적 서브셋) -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard/dist/web/variable/pretendardvariable-dynamic-subset.min.css" />

<!-- Google Fonts -->
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@600;700&family=Inter:wght@400;500;600&family=Noto+Serif+KR:wght@700;900&display=swap" rel="stylesheet" />
```

### 5.3 성능 예산

| 리소스 | 예산 | 비고 |
|--------|------|------|
| HTML | 30KB | 단일 파일 |
| CSS (Tailwind) | 100KB (gzip) | CDN 캐시 |
| JS (GSAP+Lenis+Lucide) | 150KB (gzip) | defer 로딩 |
| 폰트 | 200KB | 동적 서브셋 |
| 히어로 이미지/비디오 | 300KB (poster) | lazy video |
| 기타 이미지 | 200KB (viewport) | WebP + lazy |
| **합계** | **~800KB** | 첫 로드 기준 |

### 5.4 SEO 구조화 데이터

```json
{
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
  "name": "철목수",
  "description": "스틸하우스 전문 시공, 커스텀 철제 제작",
  "telephone": "010-411-5210",
  "url": "https://cheolmoksu.com",
  "sameAs": [
    "https://www.youtube.com/@철목수",
    "https://www.instagram.com/cheolmoksu"
  ]
}
```

FAQ 섹션: `FAQPage` 스키마 적용.

---

## 6. 인터랙션 & 애니메이션 명세

### 6.1 스크롤 기반 애니메이션

| 요소 | 애니메이션 | 트리거 | 라이브러리 |
|------|----------|--------|----------|
| 히어로 텍스트 | 순차 페이드인 (0.3초 간격) | 페이지 로드 | GSAP |
| 신뢰 지표 숫자 | 카운트업 (0→목표, 2초) | 뷰포트 진입 | Intersection Observer |
| 서비스 카드 | 아래에서 위로 슬라이드 | 뷰포트 진입 | GSAP ScrollTrigger |
| 포트폴리오 카드 | 페이드인 + 약간 위로 | 뷰포트 진입 | GSAP ScrollTrigger |
| 타임라인 노드 | 좌/우 교차 슬라이드인 | 뷰포트 진입 | GSAP ScrollTrigger |
| 차별화 카드 | 순차 페이드인 (0.15초 간격) | 뷰포트 진입 | GSAP ScrollTrigger |

### 6.2 마이크로 인터랙션

| 요소 | 인터랙션 | 방식 |
|------|---------|------|
| CTA 버튼 | 호버 시 배경 어두워짐 + 미세 확대(1.02) | CSS transition |
| 카드 | 호버 시 그림자 확대 + translateY(-2px) | CSS transition |
| 포트폴리오 이미지 | 호버 시 줌(1.05) + 오버레이 | CSS transition |
| 내비 링크 | 호버 시 밑줄 슬라이드 | CSS ::after |
| FAQ 아코디언 | 클릭 시 높이 애니메이션 | CSS max-height transition |
| Before/After 슬라이더 | 드래그로 비교 | Pointer events JS |

### 6.3 페이지 전환

- Lenis 스무스 스크롤 (전체 페이지)
- 앵커 링크 클릭 시 부드러운 스크롤 이동
- 내비게이션 스크롤 시 헤더 축소 애니메이션

---

## 7. 반응형 브레이크포인트

| 브레이크포인트 | 레이아웃 변화 |
|-------------|-------------|
| < 640px (모바일) | 단일 열, 스티키 바 표시, 햄버거 메뉴, 터치 최적화 |
| 640-768px (태블릿) | 2열 그리드 시작, 카드 2x 배치 |
| 768-1024px (태블릿 가로) | 사이드바 레이아웃 가능, 타임라인 좌우 교차 |
| 1024-1280px (데스크톱) | 3열 그리드, 풀 내비게이션, 스티키 바 숨김 |
| > 1280px (와이드) | max-width 1200px 센터 정렬, 여백 확대 |

---

## 8. 콘텐츠 체크리스트 (클라이언트 제공 필요)

- [ ] 완공 스틸하우스 고화질 사진 (최소 5개 프로젝트)
- [ ] 시공 과정 사진 (단계별)
- [ ] 커스텀 철제 제작 사진 (가대, 계단, 펜스, 가구)
- [ ] Before/After 사진 세트 (최소 2개 프로젝트)
- [ ] 히어로 비디오 (15-30초, 시공 타임랩스 또는 하이라이트)
- [ ] 유튜브 영상 URL (시공 과정별 대표 영상 8개)
- [ ] 고객 후기 텍스트 (최소 3건, 이름/지역/건축유형 포함)
- [ ] 시공 실적 수치 (총 시공 건수, 경력 년수, 만족도)
- [ ] 사업자등록번호
- [ ] 카카오톡 채널 ID
- [ ] 사무실/공장 주소 (네이버 지도용)
- [ ] 로고 파일 (SVG 또는 고해상도 PNG)

---

## 9. 구현 우선순위

| 단계 | 범위 | 산출물 |
|------|------|--------|
| Phase 1 | 정적 구조 | HTML + Tailwind 마크업 (전 섹션) |
| Phase 2 | 스타일링 | 반응형 디자인 + 다크/라이트 섹션 교차 |
| Phase 3 | 인터랙션 | GSAP 애니메이션 + Before/After 슬라이더 |
| Phase 4 | 기능 | 멀티스텝 폼 + FAQ 아코디언 + 스티키 바 |
| Phase 5 | 최적화 | 이미지 최적화 + 성능 튜닝 + SEO 구조화 데이터 |
| Phase 6 | 배포 | 도메인 연결 + 카카오/네이버 연동 |

---

*기획서 v2 작성 완료. 이 문서를 기반으로 구현을 진행합니다.*
