# ODE 사이트 구조 (DvpHm/ODE)

라이브: https://DvpHm.github.io/ODE/
최종 정리: 2026-06-28

전부 정적 파일(서버 0). 데이터는 localStorage + GitHub API 기반.

---

## 🌐 공개 페이지

| 파일                       | 용도                                                                 |
|--------------------------|--------------------------------------------------------------------|
| `index.html`             | 아트머그 임베드용 공개 커미션 페이지 (`data/commission.json`, `data/file.json` 읽음) |
| `home.html`              | 홈/포털 페이지                                                           |

## 🛠 스튜디오 (작업 관리 — 비공개 도구)

`studio.html` = 통합 작업실 셸. 아래 8개를 iframe 탭으로 묶음:

| 탭 | 파일 | 용도                                                  |
|----|------|-----------------------------------------------------|
| 대시보드 | `d_e5f91a26c0bc49a9.html` | 의뢰 관리 (비공개 난수 주소)                                   |
| 오늘 | `today.html` | ADHD 오늘 모드 — 가장 급한 칩 1개 + 포커스 타이머 + 미완료 이월 + 작업 스트릭 |
| 플래너 | `planner.html` | 할일 태그·캘린더 DnD·AI 추출·인벤토리·대시보드 연동                    |
| 연습트래커 | `practice.html` | 연습 타이머·기록                                           |
| 커미션편집 | `commission-editor.html` | 가격/메뉴/약관 편집 → `data/commission.json`                |
| 포트폴리오 | `portfolio-manager.html` | 포트폴리오 관리 → `data/file.json`                         |
| 통계 | `stats.html` | 통계                                                  |
| 견적서 | `quote.html` | 견적서(PNG)                                            |

| 파일 | 용도 |
|------|------|
| `dashboard.html` | `d_e5f…`의 배포(baked) 산출본 — 자동 생성되므로 직접 수정 X |

## 📁 데이터 / 기타

| 항목 | 용도                              |
|------|---------------------------------|
| `data/` | `commission.json`, `file.json` 등 |
| `portfolio/` | 이미지          |
| `manifest.json`, `sw.js`, `service-worker.js`, `icons/` | PWA 관련                          |
| `build_studio.py` | 스튜디오 빌드 스크립트                    |

## 🗄 archive/ — 미사용·구버전 (2026-06-12 이동)

어디서도 링크되지 않는 BETA/백업 파일. 되돌리려면 루트로 다시 옮기면 됨.

| 파일 | 비고 |
|------|------|
| `home-BETA.html` | `home.html`의 구 베타본 |
| `index133.html` | 옛 index 백업 (200KB) |
| `deadline.html` | 마감캘린더 — 플래너 캘린더와 중복되어 "오늘" 탭으로 대체(2026-06-12) |

---

### 참고 (정리 여지)
- `sw.js`와 `service-worker.js`가 둘 다 있음 — PWA 서비스워커 중복 가능성. 어느 쪽이 실제 등록되는지 확인 후 하나로 통일하면 깔끔.
