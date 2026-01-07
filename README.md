# 🔐 **Secure_entry_system**
> STM32 기반 임베디드 출입 인증 제어 시스템

---
## 📌 1. 프로젝트 목표

- STM32 기반 출입 인증 시스템의 전체 동작 흐름 설계 및 구현
- 사용자 입력 → 인증 판단 → 제어 출력까지의 임베디드 제어 로직 이해
- GPIO, 인터럽트, 타이머 등 MCU 핵심 주변장치 활용 능력 강화
- 인증 성공/실패에 따른 상태 분기 및 예외 처리 로직 구현

---
## 🎬 2. 시연 영상

 https://github.com/user-attachments/assets/67d784ac-4380-4812-8d79-416c29d028aa

---
## 🧠 3. 전자 회로도
> STM32를 중심으로 입력 장치(카드/버튼),
> 출력 장치(LED, Buzzer), 전원부로 구성된
> 출입 인증 시스템의 하드웨어 기반 시스템 아키텍처입니다.

<img width="1702" height="1174" alt="image" src="https://github.com/user-attachments/assets/1c657189-d32d-4e12-bad1-26f7ff2867c6" />

 ---
## 🔧 4. 핵심 기능
 
### ⚙️ Device (입력 · 인증 · 제어)
- 카드 입력 신호를 GPIO로 수신하고, 인터럽트 기반 이벤트 처리를 통해 실시간 입력을 감지
- 사전 등록된 인증 데이터와 입력 정보를 비교하여 인증 성공 / 실패 상태 판단 로직 구현 
- 인증 결과에 따라 릴레이·전자락·서보모터 등 출입 제어 장치 출력 신호 제어  
- 입력 → 인증 → 출력으로 이어지는 임베디드 제어 흐름을 MCU 단에서 직접 구현 

### 🚦 State Management (FSM)
- 대기 → 입력 → 인증 → 허용 / 거부 단계로 구성된 FSM(State Machine) 기반 상태 관리 구조 설계   
- 상태별 동작을 명확히 분리해 로직 가독성과 확장성 확보 
- 인증 실패, 재입력 등 예외 흐름을 고려한 상태 전이 처리 
  
### 🔔 Feedback (상태 표시)
- LED를 통해 시스템 상태 (대기 / 인증 성공 / 인증 실패) 시각적으로 표시 
- 부저(Buzzer)를 이용해 인증 성공·실패에 따른 즉각적인 음향 피드백 제공  
- 사용자 입력에 대한 즉각적인 반응 구조 구현

### 🛠 System Environment
- STM32CubeIDE 기반 프로젝트 구성 및 빌드
- GPIO, 인터럽트, 타이머 등 MCU 핵심 주변장치 직접 설정 및 제어 
- USB 또는 외부 전원을 통한 시스템 구동
  
---
 ## 🧩 기술 요약
- Platform: STM32 MCU
- Language: C
- Development: STM32CubeIDE
- Input Handling: GPIO, Interrupt
- Control Logic: FSM (State Machine)
- Output Control: LED, Buzzer 


