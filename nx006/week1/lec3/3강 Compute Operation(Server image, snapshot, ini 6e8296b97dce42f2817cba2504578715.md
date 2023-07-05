# 3강. Compute Operation(Server image, snapshot, init script 등) 소개

URL: https://www.edwith.org/essentialhandson/lecture/338867
강의 시간: 11:05

![Untitled](./3%EA%B0%95%20Compute%20Operation/Untitled.png)

### 서버 이미지

- 만든 VM 서버의 전체 이미지
- 서버 이미지 생성 시 운영 중 상태에서 쉽게 서버 이미지 생성 가능
- 새 이미지 생성 시 기존 서버 이미지와 관계 없이 서버 타입 변경 가능
- 한국 리전에서 만든 서버 이미지 역시 다른 리전에서 이미지 공유 가능

### 스냅샷

- 특정 볼륨에 대해서 하나의 카피본을 만드는 과정
- 서버가 운영 중인 상태에서 스냅샷 뜨기 가능
- 리전 간 공유는 가능하나, 디스크 사이즈 변경 불가능

### 유사 서버

- 어느 서버가 가지고 있는 특징(특성, 어떤 디스크 타입인 지 등), 템플릿을 떠오는 것

### Server Image Builder

오픈 소스 도구인 Packer, Terraform 등을 통해서 서버 이미지를 생성 가능

---

## Init Script

![Untitled](./3%EA%B0%95%20Compute%20Operation/Untitled%201.png)

Init Script 작성으로 쉽게 공통된 서버 생성 가능

---

### ACG

![Untitled](./3%EA%B0%95%20Compute%20Operation/Untitled%202.png)

서버의 방화벽 역할

- NACL은 우선순위가 있는 반면 ACG는 우선순위가 없음

---

### 추가 스토리지 구성

![Untitled](./3%EA%B0%95%20Compute%20Operation/Untitled%203.png)

- 블록 스토리지에 해당됨
- 블록 스토리지는 최대 2TB까지 생성 가능하나, 추가적인 용량 필요 시 추가적인 스토리지를 구매해서 붙일 수 있음
- 블록 스토리지는 원하는 서버에다가 뗐다 붙였다 가능함
    - 한 서버에서 detach 후 다른 서버로 attach 가능

---

### Auto Scailing

![Untitled](./3%EA%B0%95%20Compute%20Operation/Untitled%204.png)

Auto Scaling을 사용하기 위해서는 상기 세 가지 설정만 해주면 됨

1. Launch Configuration
    1. 서버의 템플릿 만들기
    2. Server의 init Script도 이 단계에서 해준다
2. Autoscailing Server Group
    1. 여러 서버를 그룹으로 관리
    2. 서버의 최소/최대 대수, 기대 용량(desiredCapacity, 최초 대수) 등을 생성 가능
3. Event Rule
    1. 언제 서버를 증가, 감수시킬 것인지 액션의 기준이 되는 모니터링 메트릭을 생성

---

### Kubernetes Service

![Untitled](./3%EA%B0%95%20Compute%20Operation/Untitled%205.png)

- 완전 관리형 쿠버네티스 서비스