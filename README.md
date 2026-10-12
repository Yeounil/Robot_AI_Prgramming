# Robot AI Programming

SO-101 로봇 팔과 [LeRobot](https://github.com/huggingface/lerobot)으로 시연 데이터를 수집하고, 모방학습 정책(ACT, SmolVLA)을 학습·평가하는 과제 저장소입니다.

- 학번 / 이름: 2021136117 / 정승일
- Hugging Face: [Yeounil](https://huggingface.co/Yeounil)

## 폴더 구조

```
robot-ai-programming/
├── README.md
├── .gitignore
├── assignments/              # 과제 제출 노트북 (실행 결과 포함해 커밋)
│   ├── assignment_1.ipynb
│   ├── assignment_2.ipynb
│   ├── ...
│   └── images/               # 노트북에 삽입하는 사진 (setup.jpg 등)
├── scripts/                  # 녹화·학습·평가 실행 스크립트 (lerobot-record 등)
├── configs/                  # 학습·평가 설정 파일
│
├── data/                     # 로컬 데이터셋 사본          ─┐
├── outputs/                  # 학습 결과, 체크포인트        │ git 제외
├── wandb/                    # wandb 로그                   │ (.gitignore)
└── venv/                     # 노트북 실행용 Python 환경   ─┘
```

**규칙**
- 데이터셋과 모델 체크포인트는 GitHub에 올리지 않고 Hugging Face Hub에 올립니다.
- 과제 노트북은 `assignments/assignment_N.ipynb` 이름으로, 모든 셀을 실행해 출력이 보이는 상태로 커밋합니다.
- 노트북에 들어가는 이미지는 `assignments/images/`에 두고 상대 경로(`images/파일명`)로 참조합니다.

## 과제 목록

| 과제 | 내용 | 노트북 | 결과물 | 상태 |
|---|---|---|---|---|
| 1 | 시연 데이터 수집 및 Hub 업로드 | [assignment_1.ipynb](assignments/assignment_1.ipynb) | [Yeounil/pick-cube_20261008_100102](https://huggingface.co/datasets/Yeounil/pick-cube_20261008_100102) | 완료 |
| 2 | 미정 | - | - | 예정 |
| 3 | 미정 | - | - | 예정 |
| 4 | 미정 | - | - | 예정 |
| 5 | 미정 | - | - | 예정 |

## 수집 환경

- **로봇**: SO-101 follower / leader (텔레오퍼레이션)
- **카메라** (640×480, 30fps)
  - `overhead`: 그리퍼 상단에 장착 (이름과 달리 팔과 함께 움직임)
  - `wrist`: 로봇 전방에 고정
- **태스크**: 테이블 위의 큐브를 집어 반대쪽으로 옮기기 (`"Grab the black cube"`)

## 개발 환경

노트북은 `venv/`의 Python 3.11 커널로 실행합니다.

```bash
uv venv venv --python 3.11
uv pip install --python venv/bin/python ipykernel ipywidgets pandas pyarrow matplotlib huggingface_hub
```
