# MacGyvBot Docs

MacGyvBot 프로젝트의 기획 문서, 요구사항 명세서, 최종 발표용 HTML 데크를 관리하는 문서 저장소입니다.

MacGyvBot은 사용자의 공구 요청과 반납을 처리하는 ROS 2 기반 로봇팔 어시스턴트입니다. 음성 명령, 공구 인식, task coordination, manipulation, safety recovery를 연결해 공구 관리 작업 루프를 닫는 것을 목표로 합니다.

## 저장소 구성

```text
.
├── PROJECT_PROPOSAL.md
├── REQUIREMENT_SPECIFICATION.md
├── CONTRIBUTING.md
├── MACGYVBOT-DECK/
│   ├── index.html
│   ├── assets/
│   │   └── macgyvbot.png
│   └── styles/
│       ├── common.css
│       └── deck.css
└── assets/
    └── requirements-image-1.png
```

## 주요 문서

- [PROJECT_PROPOSAL.md](./PROJECT_PROPOSAL.md): 프로젝트 배경, 범위, 성공 기준, 단계별 구현 전략
- [REQUIREMENT_SPECIFICATION.md](./REQUIREMENT_SPECIFICATION.md): 시스템 구성, 기능/비기능 요구사항, 제약 사항
- [MACGYVBOT-DECK/index.html](./MACGYVBOT-DECK/index.html): 최종 발표용 16:9 HTML 슬라이드 데크
- [CONTRIBUTING.md](./CONTRIBUTING.md): 브랜치, 커밋, PR, 안전 관련 협업 규칙

## 발표 자료 실행

발표 데크는 별도 빌드 과정이 없는 정적 HTML입니다.

```bash
cd MACGYVBOT-DECK
python3 -m http.server 8000
```

브라우저에서 아래 주소를 엽니다.

```text
http://localhost:8000
```

파일을 직접 열어도 대부분 동작하지만, 로컬 서버로 여는 방식을 권장합니다.

## 발표 자료 조작

- 다음 슬라이드: `ArrowRight`, `PageDown`, `Space`, `Enter`
- 이전 슬라이드: `ArrowLeft`, `PageUp`, `Backspace`
- 첫 슬라이드: `Home`
- 마지막 슬라이드: `End`
- 특정 슬라이드 이동: `#슬라이드번호` 사용, 예: `http://localhost:8000/#5`

## 발표 자료 수정 가이드

- 슬라이드 내용은 [MACGYVBOT-DECK/index.html](./MACGYVBOT-DECK/index.html)의 `<section class="slide">` 단위로 수정합니다.
- 공통 색상, 폰트, 카드, 플로우, 표 스타일은 [MACGYVBOT-DECK/styles/common.css](./MACGYVBOT-DECK/styles/common.css)에 있습니다.
- 데크 화면 비율, 슬라이드 프레임, 네비게이션, 인쇄 모드는 [MACGYVBOT-DECK/styles/deck.css](./MACGYVBOT-DECK/styles/deck.css)에 있습니다.
- 발표 이미지와 로고는 `MACGYVBOT-DECK/assets/` 아래에 둡니다.

## 프로젝트 환경 요약

- OS: Ubuntu 22.04
- ROS 2: Humble
- Python: 3.10
- 로봇팔: Doosan Robotics M0609
- 그리퍼: OnRobot RG2
- 카메라: Intel RealSense D435I
- 주요 기능: command parsing, task queue, YOLO/SAM 기반 perception, MoveIt 기반 manipulation, collision/recovery safety

## 협업 규칙

문서 수정도 일반 코드 변경과 동일하게 [CONTRIBUTING.md](./CONTRIBUTING.md)를 따릅니다.

- 문서 변경 커밋 타입은 `docs`를 사용합니다.
- 발표 자료 스타일 변경은 기능 변경과 분리해서 리뷰하기 쉽게 유지합니다.
- 로봇 동작, 사용자 전달, 안전 제한과 관련된 설명을 바꿀 때는 실제 구현 상태와 검증 결과를 함께 확인합니다.
