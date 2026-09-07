# AI Smart Monitor Arm

## AI 인식 기반 자율 제어 기능의 지능형 모니터 암

사용자의 얼굴, 자세 및 위치 변화를 인식하고 모니터의 높이, 거리, 회전 및 각도를 자동으로 조절할 수 있도록 설계한 지능형 모니터 암 프로젝트입니다.

본 프로젝트는 기계공학 졸업작품으로 진행되었으며, 기계 구동 메커니즘과 센서 기반 제어, AI 사용자 인식 기술을 하나의 시스템으로 통합하는 것을 목표로 하였습니다.

프로젝트의 설계 결과를 기반으로 「AI 인식 기반 자율 제어 기능의 지능형 모니터 암」에 대한 특허를 출원하였습니다.

---

## 1. Project Overview

기존 모니터 암은 사용자가 직접 모니터의 위치와 각도를 조절해야 하기 때문에 사용자의 자세가 변화할 때마다 반복적으로 위치를 조정해야 합니다.

특히 병상 환자, 고령자 또는 거동이 불편한 사용자의 경우 직접 모니터 암을 조작하는 데 어려움이 발생할 수 있습니다.

본 프로젝트에서는 이러한 문제를 해결하기 위해 사용자의 얼굴, 자세 및 위치를 인식하고, 인식된 정보를 기반으로 모니터의 위치와 각도를 자동으로 조절할 수 있는 지능형 모니터 암을 설계하였습니다.

리니어 액추에이터와 서보모터를 활용하여 높이, 거리, 수평 회전 및 각도를 각각 조절할 수 있는 다축 구동 구조를 구성하고, 카메라와 센서를 통해 획득한 사용자 및 위치 정보를 제어 시스템과 연계하도록 설계하였습니다.

---

## 2. Project Goals

본 프로젝트의 주요 목표는 다음과 같습니다.

- 사용자 얼굴 및 자세 변화 인식
- 모니터 높이 자동 조절
- 사용자와 모니터 사이의 거리 조절
- 모니터 암의 수평 회전 제어
- 모니터 방향 및 각도 조절
- 저장 위치 자동 복귀
- 주변 장애물 감지 및 충돌 방지
- 사용자의 위치 변화에 따른 자동 추적
- 부드러운 조작성과 안정적인 정지 성능 확보
- 기계설계, 센서, AI 및 제어 시스템의 통합

---

## 3. Problem Definition

### 3.1 반복적인 수동 조작

일반적인 모니터 암은 사용자가 직접 모니터를 움직여 원하는 위치를 설정해야 합니다.

사용자의 자세나 위치가 변하면 모니터의 높이, 거리 및 각도를 다시 조정해야 하기 때문에 반복적인 수동 조작이 필요합니다.

특히 거동이 불편한 사용자에게 이러한 조작 방식은 사용상의 제약으로 작용할 수 있습니다.

### 3.2 미세 조작과 안정적인 정지의 상충

모니터 암의 위치를 안정적으로 유지하기 위해 높은 마찰력이나 댐핑력을 적용하면 미세한 위치 조절이 어려워질 수 있습니다.

반대로 구동 저항을 낮추면 사용자가 쉽게 조작할 수 있지만 빠르게 이동한 이후 관성으로 인해 흔들림이나 진동이 발생할 가능성이 있습니다.

따라서 부드러운 조작성과 안정적인 정지 성능을 동시에 고려한 설계가 필요합니다.

### 3.3 사용자 위치 변화에 대한 대응

기존의 수동형 모니터 암은 사용자가 이동하거나 자세를 변경하더라도 이를 자동으로 인식하여 모니터 위치를 변경하기 어렵습니다.

본 프로젝트에서는 사용자 인식 정보를 기계 구동부와 연계하여 이러한 문제를 개선하고자 하였습니다.

### 3.4 자동 이동 시 충돌 가능성

모니터 암이 자동으로 이동할 경우 주변 물체 또는 사용자와 충돌할 가능성이 있기 때문에 센서를 이용한 장애물 감지와 안전한 이동 제어가 필요합니다.

---

## 4. System Architecture

시스템은 크게 다음과 같은 구성요소로 설계하였습니다.

1. Base Unit
2. Height Adjustment Unit
3. Horizontal Rotation Unit
4. Distance Adjustment Unit
5. Angle Adjustment Unit
6. Monitor Mount
7. AI User Recognition Unit
8. Position Sensor
9. Obstacle Detection Sensor
10. Control Unit

전체 시스템의 기본 작동 흐름은 다음과 같습니다.

User
↓
AI User Recognition
↓
Face / Posture / Position Analysis
↓
Target Monitor Position Calculation
↓
Obstacle Detection
↓
Motion Command
↓
Actuator & Servo Motor Control
↓
Monitor Position Adjustment
↓
Encoder Feedback
↓
Target Position

센서에서 측정된 정보와 사용자의 상태를 제어부에서 분석하고, 계산된 목표 위치를 기반으로 각 구동부를 제어하는 구조입니다.

---

## 5. Mechanical Design

### 5.1 Base Unit

Base Unit은 전체 모니터 암을 지지하는 기본 구조입니다.

책상, 벽면 또는 침대 프레임 등에 고정할 수 있도록 구성하고, 높이조절부와 기타 구동부가 안정적으로 작동할 수 있도록 전체 시스템을 지지합니다.

---

### 5.2 Height Adjustment Unit

모니터의 높이를 조절하기 위해 리니어 액추에이터 기반의 직선 구동 구조를 적용하였습니다.

사용자의 자세 또는 위치가 변화하면 목표 모니터 높이를 계산하고, 리니어 액추에이터의 직선 운동을 통해 모니터의 높이를 조절할 수 있도록 설계하였습니다.

엔코더를 이용하여 현재 높이를 확인하고 목표 위치와 비교할 수 있도록 구성하였습니다.

Linear Actuator
↓
Vertical Motion
↓
Monitor Height Adjustment

---

### 5.3 Horizontal Rotation Unit

사용자가 좌우 방향으로 이동할 경우 모니터가 사용자의 위치를 따라 회전할 수 있도록 수평 회전 구조를 설계하였습니다.

서보모터를 이용하여 회전력을 발생시키고, 모니터 암의 수평 방향을 조절하도록 구성하였습니다.

이를 통해 사용자 얼굴의 위치 변화에 대응하여 모니터의 방향을 조절할 수 있습니다.

Servo Motor
↓
Horizontal Rotation
↓
User Tracking

---

### 5.4 Distance Adjustment Unit

모니터와 사용자 사이의 거리를 조절하기 위한 직선 구동 구조입니다.

리니어 액추에이터를 이용하여 모니터 암을 확장 또는 수축시키고, 사용자의 위치에 따라 적절한 시청 거리를 확보할 수 있도록 설계하였습니다.

Linear Actuator
↓
Extension / Retraction
↓
Viewing Distance Adjustment

---

### 5.5 Angle Adjustment Unit

모니터의 방향 및 각도를 조절하기 위해 서보모터와 기어 기반의 회전 구조를 적용하였습니다.

구동 방향을 변환할 수 있도록 베벨기어를 적용하여 모니터 마운트의 방향을 조절할 수 있도록 설계하였습니다.

Servo Motor
↓
Gear Transmission
↓
Monitor Angle Adjustment

---

### 5.6 Monitor Mount

Monitor Mount는 실제 모니터가 장착되는 부분으로, 각도조절부와 연결하여 사용자의 시청 방향에 맞게 모니터의 방향을 조절할 수 있도록 구성하였습니다.

---

## 6. AI User Recognition

사용자의 상태를 인식하기 위한 사용자 인식 시스템은 카메라 및 거리 정보를 활용하도록 설계하였습니다.

인식 대상은 다음과 같습니다.

- 사용자 얼굴 위치
- 사용자 자세
- 사용자 위치
- 사용자와 모니터 사이의 거리
- 시선 방향
- 좌우 이동 여부

사용자 인식 시스템은 다음과 같은 구조를 기반으로 합니다.

RGB Camera
+
Depth Sensor
+
AI Processing
↓
User Information

얼굴 검출 및 자세 추정을 위해 CNN 기반 얼굴 검출 방식과 OpenPose 또는 MediaPipe 기반의 자세 추정 알고리즘 등을 적용할 수 있도록 시스템을 구성하였습니다.

---

## 7. Control System

사용자 인식 결과와 각 센서 정보를 이용하여 목표 모니터 위치를 계산하고 각 구동부를 제어하도록 설계하였습니다.

기본적인 제어 흐름은 다음과 같습니다.

사용자 감지
↓
얼굴 / 자세 / 위치 분석
↓
현재 모니터 위치 확인
↓
목표 모니터 위치 계산
↓
주변 장애물 확인
↓
구동 경로 결정
↓
액추에이터 및 서보모터 구동
↓
엔코더 위치 피드백
↓
목표 위치 도달

사용자의 위치가 변화하면 사용자 인식 시스템에서 새로운 위치 정보를 획득하고 제어부에서 목표 위치를 다시 계산하도록 구성하였습니다.

---

## 8. Position Feedback

각 구동부의 현재 위치를 확인하기 위해 엔코더 기반의 위치 피드백 시스템을 적용하도록 설계하였습니다.

엔코더를 통해 다음과 같은 위치 정보를 확인할 수 있습니다.

- Height Position
- Horizontal Rotation Angle
- Distance Position
- Monitor Angle

현재 위치와 목표 위치를 비교함으로써 반복적인 위치 제어 및 저장 위치 복귀가 가능하도록 구성하였습니다.

---

## 9. Obstacle Detection

자동 구동 과정에서 주변 물체와의 충돌 위험을 줄이기 위해 근접센서를 활용한 장애물 감지 기능을 포함하도록 설계하였습니다.

기본적인 동작 과정은 다음과 같습니다.

Target Position
↓
Movement Path
↓
Obstacle Detection
↓
Path Check
↓
Motion Control

이동 경로상에 장애물이 존재하는 경우 센서 정보를 기반으로 이동을 제한하거나 다른 이동 경로를 검토할 수 있도록 시스템을 구성하였습니다.

---

## 10. Position Memory

사용자가 자주 사용하는 모니터 위치를 저장하고 필요할 때 해당 위치로 자동 복귀할 수 있도록 위치 메모리 기능을 고려하였습니다.

예를 들어 다음과 같은 사용자 환경에 적용할 수 있습니다.

- TV 시청 위치
- 영상 통화 위치
- 업무 위치
- 휴식 위치
- 병상 사용 위치

각 구동부의 엔코더 정보를 이용하여 저장된 위치를 재현할 수 있도록 설계하였습니다.

---

## 11. Wireless Control

사용자가 직접 모니터 암을 조작하기 어려운 경우를 고려하여 무선 통신 기반의 제어 기능을 적용할 수 있도록 구성하였습니다.

BLE 등의 무선 통신을 활용하여 스마트폰 애플리케이션 또는 별도의 리모컨에서 제어 명령을 전달할 수 있도록 설계하였습니다.

Smartphone / Remote Controller
↓
Wireless Communication
↓
Control Unit
↓
Monitor Arm

---

## 12. Motion Stability

모니터 암은 부드러운 이동과 이동 후 안정적인 정지라는 두 가지 요구사항을 동시에 고려해야 합니다.

본 프로젝트에서는 이동 속도에 따라 구동 저항이 변화할 수 있는 속도 감응형 댐핑 개념을 적용하여 기계적 안정성을 향상시키는 구조를 제안하였습니다.

저속 이동에서는 상대적으로 부드러운 조작이 가능하도록 하고, 고속 이동 시에는 높은 저항을 발생시켜 이동 후 발생할 수 있는 흔들림을 억제하는 것을 목표로 설계하였습니다.

세부적인 특허 구조 및 설계 치수는 본 Repository에서 공개하지 않습니다.

---

## 13. Main Operating Scenario

### Scenario 1. Posture Change

사용자가 누운 자세에서 앉은 자세로 변경
↓
사용자 자세 변화 감지
↓
목표 시청 위치 계산
↓
모니터 높이 및 각도 조절
↓
최적 시청 위치 확보

### Scenario 2. User Tracking

사용자가 좌우로 이동
↓
사용자 얼굴 위치 감지
↓
얼굴 중심 위치 계산
↓
수평 회전부 제어
↓
모니터 방향 조절

### Scenario 3. Saved Position

사용자가 저장 위치 선택
↓
목표 위치 정보 호출
↓
현재 위치 확인
↓
이동 경로 확인
↓
각 구동부 제어
↓
저장 위치로 자동 복귀

---

## 14. Key Features

본 프로젝트의 주요 특징은 다음과 같습니다.

- AI 기반 사용자 얼굴 및 자세 인식
- 다축 모니터 위치 조절
- 리니어 액추에이터 기반 높이 조절
- 리니어 액추에이터 기반 거리 조절
- 서보모터 기반 수평 회전
- 기어 기반 모니터 각도 조절
- 엔코더 기반 위치 피드백
- 저장 위치 자동 복귀
- 근접센서 기반 장애물 감지
- 무선 기반 사용자 제어
- 사용자의 위치 변화에 따른 자동 추적
- 조작성 및 정지 안정성을 고려한 기계 구조 설계

---

## 15. Engineering Approach

본 프로젝트에서는 단순히 모니터 암을 전동화하는 것이 아니라 기계 시스템과 센서, AI 및 제어 시스템의 통합을 고려하였습니다.

Problem Definition
↓
Mechanical Concept Design
↓
Actuator Selection
↓
Sensor Integration
↓
AI User Recognition Concept
↓
Control Architecture Design
↓
Safety Consideration
↓
System Integration
↓
Patent Application

기계구조 자체의 설계뿐 아니라 구동계, 센서 피드백, 사용자 인식 및 제어 시스템 간의 상호작용을 고려하는 시스템 엔지니어링 관점으로 프로젝트를 진행하였습니다.

---

## 16. Engineering Skills

본 프로젝트를 통해 다음과 같은 공학적 역량을 다루었습니다.

### Mechanical Engineering

- 기구설계
- 다축 구동 메커니즘
- 리니어 액추에이터 활용
- 서보모터 활용
- 기어 기반 동력 전달
- 모니터 암 구조 설계
- 구동 안정성 검토

### Mechatronics

- 액추에이터와 센서 통합
- 엔코더 기반 위치 피드백
- 센서 기반 자동제어
- 다축 모션 시스템 구성

### AI & Control

- 사용자 인식 기반 제어 개념
- 얼굴 위치 추적
- 자세 인식
- 목표 위치 계산
- 자동 위치 조절
- 장애물 감지 및 이동 제어

### Engineering Documentation

- 문제 정의
- 아이디어 구체화
- 시스템 구성
- 기술 구조 정리
- 특허 출원

---

## 17. Project Result

본 프로젝트를 통해 AI 사용자 인식 기술과 다축 기계 구동 시스템을 결합한 지능형 모니터 암 시제품을 제작하였습니다.

리니어 액추에이터와 서보모터를 이용한 다축 구동 구조를 설계하고, 사용자 인식 및 제어 시스템과 연계하여 자동 모드와 수동 모드에서 실제 구동을 확인하였습니다.

### Prototype Demonstration

#### 1. Automatic User Tracking Mode

사용자의 움직임을 인식하고 모니터 암이 자동으로 대응하는 작동 영상입니다.

▶ [자동 추적 모드 작동 영상](04_results/01_auto_tracking_demo.mp4)

#### 2. Manual Control Mode

사용자가 제어 인터페이스를 통해 모니터 암을 직접 조작하는 작동 영상입니다.

▶ [수동 제어 모드 작동 영상](04_results/02_manual_control_demo.mp4)

### Project Outcomes

- 다축 모니터 암 기구 구조 설계
- 리니어 액추에이터 및 서보모터 기반 구동 시스템 구성
- 사용자 인식 기반 자동 제어 기능 적용
- 수동 제어 기능 적용
- 실제 시제품 제작 및 구동 확인
- 설계 결과를 기반으로 특허 출원

---

## 18. Patent

본 졸업작품의 설계 및 개발 결과를 기반으로 지능형 모니터 암에 대한 특허를 출원하였습니다.

### Patent Title

**AI 인식 기반 자율 제어 기능의 지능형 모니터 암**

**Intelligent Monitor Arm with AI Recognition-Based Autonomous Control**

### Application Information

- **출원번호:** 10-2026-0003663
- **출원일:** 2026.01.08
- **출원인:** 한남대학교 산학협력단
- **출원상태:** 특허 출원 및 심사청구
- **구분:** 대한민국 특허 출원

### Patent Overview

본 특허는 사용자의 얼굴, 자세 및 위치 정보를 기반으로 모니터의 위치를 자동으로 조절할 수 있는 다축 모션 기반 지능형 모니터 암에 관한 것입니다.

기계 구동부와 사용자 인식 시스템, 위치 센서 및 제어부를 연계하여 사용자의 상태 변화에 대응할 수 있는 시스템 구조를 제안하였습니다.

주요 기술 개념은 다음과 같습니다.

- 다축 모니터 위치 조절 구조
- AI 기반 사용자 얼굴 및 자세 인식
- 엔코더 기반 위치 피드백
- 사용자 위치에 따른 자동 추적
- 저장 위치 자동 복귀
- 주변 장애물 감지
- 무선 기반 사용자 제어
- 구동 안정성을 고려한 기계 구조

특허권 및 향후 심사 절차를 고려하여 상세 청구범위, 세부 치수 및 일부 내부 설계정보는 본 Repository에서 공개하지 않습니다.

---

## 19. Repository Structure

ai-smart-monitor-arm/

├── README.md
├── 01_overview/
├── 02_design/
├── 03_control/
└── 04_results/

### 01_overview

프로젝트 개요, 시스템 구성도 및 전체 프로젝트 설명 자료를 저장합니다.

### 02_design

공개 가능한 CAD 이미지, 기계구조 및 설계 관련 자료를 저장합니다.

### 03_control

제어 흐름도, 센서 구성 및 AI 사용자 인식 시스템 관련 자료를 저장합니다.

### 04_results

완성품 이미지, 시험 결과, 발표 자료 및 공개 가능한 프로젝트 결과물을 저장합니다.

---

## 20. Project Keywords

Mechanical Design  
Mechatronics  
Smart Monitor Arm  
Linear Actuator  
Servo Motor  
Encoder  
Sensor  
Motion Control  
AI Recognition  
Computer Vision  
Human Tracking  
Automatic Positioning  
Obstacle Detection  
Engineering Design  
Patent

---

## 21. Notes

본 Repository는 기계공학 졸업작품의 기술적 개념과 개발 과정을 취업 포트폴리오 목적으로 정리한 자료입니다.

특허권 및 연구 관련 사항을 고려하여 세부 치수, 상세 청구 구조 및 일부 설계자료는 공개하지 않습니다.