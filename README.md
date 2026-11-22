# Vertical Shooter (S/W engineering proj 1)

화면 아래쪽 플레이어 비행기를 좌우로 움직이며 총알을 쏘아, 위에서 내려오는 적을 맞히는 종스크롤 슈팅 게임.


## 실행 방법

- Python 3.10–3.13, pygame 2.x
  - Python 3.14 에서는 pygame 2.6.1 이 설치되지 않으니, 3.10–3.13 중 하나를 사용할 것.

```bash
python -m pip install pygame==2.6.1
python main.py
```

## 조작

| 키 | 동작 |
|---|---|
| ← / → | 좌우 이동 |
| Space | 시작 화면에서 게임 시작 / 게임 중 총알 발사 |
| R | 게임 오버 후 다시 시작 |
| Esc | 종료 (시작 화면에서도) |

## 파일 구성

| 파일 | 내용 |
|---|---|
| `main.py` | 게임 루프 — 입력 처리, 갱신, 그리기, 점수·생명·게임 오버 |
| `entities.py` | 그림 불러오기(`load_frame`), 배경(`Background`), 스프라이트 클래스 — `Player`, `Bullet`, `Enemy` |
| `settings.py` | 화면 크기·속도·색 같은 상수 |
| `assets/` | 그림 — ansimuz CC0 픽셀 아트 (출처: `assets/CREDITS.md`) |
| `AI_USAGE.md` | 생성형 AI 사용 기록 |

## 구현한 기능


- [x] F1 플레이어 이동 — 방향키로 좌우 이동, 화면 양쪽 경계 제한
- [x] F2 총알 발사 — SPACE 한 번에 한 발, 위로 이동하며 화면 밖에서 제거
- [x] F3 적 명중과 점수 — 명중한 적과 총알 제거, 적당 10점 추가 및 점수 표시
- [x] F4 피격과 게임 오버 — 충돌·적 통과 시 생명 감소, 생명 소진 시 게임 정지 및 결과 표시
- [x] F5 재시작과 최고 점수 — 게임 오버 후 R로 초기화, 최고 점수 파일 저장 및 다음 실행에서 유지

## Windows에서 Python 버전을 지정해 실행

Python 3.12를 설치한 환경에서는 다음 명령을 사용합니다.

~~~powershell
py -3.12 -m pip install pygame==2.6.1
py -3.12 main.py
~~~

최고 점수는 main.py와 같은 폴더의 highscore.txt에 저장됩니다. 파일이 없거나 숫자가 아니면 0점으로 시작하며, 게임 오버 시 기존 기록보다 높은 점수만 저장합니다.
