# 철목수 랜딩 페이지 디자인 리서치

> 프로젝트: 철목수(Cheolmoksu) 스틸하우스 전문 시공사 랜딩 페이지
> 조사일: 2026-04-01
> 기반 자료: [kateye-analysis-cheolmoksu-20260401-001.md](../kateye-analysis-cheolmoksu-20260401-001.md)

---

## 리서치 개요

철목수의 **이중 포지셔닝**(스틸하우스 = 프리미엄, 커스텀 철제 = 가성비)을 반영한 랜딩 페이지 구축을 위해 6개 카테고리의 디자인 리서치를 수행했습니다.

### 핵심 발견 사항

| 발견 | 수치/근거 | 적용 방향 |
|------|----------|----------|
| 건설업 웹사이트 전환율 1.9%로 최하위 | Ruler Analytics 2025 | 5%+ 목표로 전환 최적화 집중 |
| 전화 리드 전환율 46% | Home services 분석 | 전화 CTA를 최우선 배치 |
| 비디오 히어로 전환율 80% 증가 | 업계 벤치마크 | 유튜브 시공 영상 히어로 활용 |
| 스틸하우스 업체 웹사이트 대부분 구형 | 한국 시장 조사 | 건축사무소급 비주얼로 차별화 |
| Sticky CTA 모바일 전환 15-25% 향상 | 전환율 최적화 연구 | 전화+카카오+견적 스티키 바 적용 |
| 고객 후기 CTA 근처 배치 시 270% 전환 증가 | 소셜 프루프 연구 | 시공 후기를 CTA와 인접 배치 |

---

## 카테고리별 리서치 목록

### 01. 랜딩 페이지 디자인 패턴
- **파일**: [01-landing-page-design-patterns/design-patterns.md](./01-landing-page-design-patterns/design-patterns.md)
- **내용**: 히어로 섹션 패턴(풀이미지/비디오/스플릿), 신뢰 요소 배치, CTA 전략, 모바일 퍼스트, 컬러 심리학
- **핵심**: "Steel Authority" 팔레트(#1C1B1A + #B08D57 + #F2EFEA) 추천, 9섹션 페이지 구조 제안
- **출처**: 26개 검증된 URL

### 02. 프리미엄 건축 브랜딩
- **파일**: [02-premium-construction-branding/branding-guide.md](./02-premium-construction-branding/branding-guide.md)
- **내용**: 타이포그래피 시스템, 컬러 팔레트, 사진/비주얼 스토리텔링, 스페이싱, 브랜드 보이스
- **핵심**: Cormorant Garamond(헤드라인) + Inter(본문), Noto Serif KR + Pretendard(한글). "Steel & Craft" 팔레트(#0d0d0d + #d9b061 + #f2efea)
- **출처**: 25+ URL (Awwwards, Webflow, IxDF 등)

### 03. 한국 건축 웹사이트 레퍼런스
- **파일**: [03-korean-construction-web-references/korean-references.md](./03-korean-construction-web-references/korean-references.md)
- **내용**: 한국 건축사무소 30개 레퍼런스, 스틸하우스 업체 현황, 한국 특화 UX(카카오/네이버), 한글 타이포그래피
- **핵심**: 기존 스틸하우스 업체가 구형 템플릿 수준 → 건축사무소급 비주얼로 차별화 기회. JOHO Architecture 디자인 패턴(GSAP + Lenis) 참고
- **출처**: Architizer, ArchDaily 등

### 04. 건축 포트폴리오 쇼케이스
- **파일**: [04-architecture-portfolio-showcase/portfolio-patterns.md](./04-architecture-portfolio-showcase/portfolio-patterns.md)
- **내용**: Before/After 갤러리, 시공 프로세스 타임라인, YouTube 임베드 최적화, 프로젝트 케이스 스터디, 이미지 그리드, 수치 프레젠테이션
- **핵심**: lite-youtube-embed로 224배 빠른 YouTube 로딩. 인터랙티브 슬라이더 + 8단계 시공 타임라인 패턴
- **출처**: 40+ URL

### 05. 전환율 최적화
- **파일**: [05-conversion-optimization/conversion-guide.md](./05-conversion-optimization/conversion-guide.md)
- **내용**: 업계 벤치마크, CTA 패턴, 리드 캡처 폼, 전화 CTA, 소셜 프루프, 모바일 최적화, 페이지 속도
- **핵심**: 전화 우선 전략(46% 전환), 3+3 멀티스텝 견적 폼(20-35% 향상), 48px+ 전화번호 헤더, 2.5초 이내 LCP
- **출처**: 40+ URL (Unbounce, LocaliQ 등)

### 06. 디자인 에셋 카탈로그
- **파일**: [06-design-assets/asset-catalog.md](./06-design-assets/asset-catalog.md)
- **내용**: 아이콘(Lucide/Heroicons/Phosphor), 스톡 사진, 배경 패턴, 애니메이션(GSAP+Lenis), 폰트 페어링, 컬러 팔레트, SVG 일러스트
- **핵심**: 전체 무료 상용 라이선스. Minimal HTML+CDN 스택 < 800KB 퍼스트 로드 목표
- **출처**: 16+ URL

---

## 추천 디자인 스택

리서치 결과를 종합한 철목수 랜딩 페이지 기술 스택:

| 영역 | 선택 | 이유 |
|------|------|------|
| **프레임워크** | Pure HTML + Tailwind CSS (CDN) | 최대 이식성, 빠른 로딩 |
| **한글 폰트** | Pretendard (본문) + Noto Serif KR (헤드라인) | 다이나믹 서브셋, 프리미엄 느낌 |
| **영문 폰트** | Inter (본문) + Cormorant Garamond (헤드라인) | x-height 매칭, 장인 브랜딩 |
| **아이콘** | Lucide Icons | ISC 라이선스, Tailwind 호환 |
| **애니메이션** | GSAP + ScrollTrigger + Lenis | 업계 표준, JOHO Architecture급 |
| **컬러** | Steel Authority (#1C1B1A + #B08D57 + #F2EFEA) | 철강+장인 정신 |
| **YouTube** | lite-youtube-embed | 224배 빠른 로딩 |

---

## 추천 페이지 구조 (9섹션)

```
1. 히어로      — 풀스크린 비디오/이미지 + "무료 상담 받기" CTA
2. 신뢰 지표   — 시공 실적 수치 (카운트업 애니메이션)
3. 서비스      — 스틸하우스 / 커스텀 철제 이중 포지셔닝
4. 포트폴리오  — Before/After 슬라이더 + 프로젝트 그리드
5. 시공 과정   — 8단계 타임라인 + YouTube 임베드
6. 차별화      — 직영 공장, 투명 시공, 엔지니어링 품질
7. 고객 후기   — 시공 사진 + 텍스트 후기
8. FAQ        — 비용, 기간, 과정 질문 아코디언
9. 연락처/CTA — 전화 + 카카오톡 + 견적 폼
   + Sticky Bar — 모바일 하단 고정 (전화/카카오/견적)
```

---

*본 리서치는 2026-04-01 기준으로 수집되었습니다. 웹 리소스 URL은 시간이 지남에 따라 변경될 수 있습니다.*
