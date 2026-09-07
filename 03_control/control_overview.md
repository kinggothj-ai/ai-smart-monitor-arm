# Control System Overview

## 1. Control Concept

본 시스템은 사용자 인식 정보와 각 구동축의 위치 정보를 기반으로 모니터의 목표 위치를 계산하고, 각 구동부를 제어하도록 설계하였습니다.

본 Repository에서는 실제 제어 소프트웨어의 구현 여부와 구분하여, 졸업작품 및 특허에서 설계한 제어 개념과 시스템 구조를 정리합니다.

---

## 2. Input Information

제어 시스템에서 활용하도록 설계한 주요 입력 정보는 다음과 같습니다.

- 사용자 얼굴 위치
- 사용자 자세
- 사용자와 모니터 사이의 거리
- 각 구동축의 현재 위치
- 주변 장애물 감지 정보
- 사용자의 위치 복귀 명령

---

## 3. User Recognition

사용자 인식부는 RGB 카메라와 깊이센서를 기반으로 사용자의 상태를 감지하도록 설계하였습니다.

주요 인식 대상은 다음과 같습니다.

- Face Position
- User Posture
- User Position
- Viewing Distance
- Movement Direction

사용자의 위치 또는 자세가 변하면 인식 정보를 제어부에 전달하여 새로운 목표 모니터 위치를 계산하는 구조입니다.

---

## 4. Position Feedback

각 구동부의 현재 위치를 확인하기 위해 엔코더 기반 위치 피드백 구조를 적용하도록 설계하였습니다.

위치 정보는 다음 구동축에 활용됩니다.

- Height Adjustment
- Horizontal Rotation
- Distance Adjustment
- Monitor Angle

현재 위치와 목표 위치를 비교하여 각 구동부의 이동량을 결정하도록 구성하였습니다.

---

## 5. Basic Control Flow

기본 제어 흐름은 다음과 같습니다.

User Detection
↓
Face / Posture / Position Recognition
↓
Current Monitor Position Check
↓
Target Position Calculation
↓
Obstacle Detection
↓
Movement Command
↓
Actuator & Servo Motor Control
↓
Encoder Feedback
↓
Target Position

---

## 6. User Tracking Mode

사용자가 좌우로 이동하는 경우 다음과 같은 흐름으로 모니터 방향을 조절하도록 설계하였습니다.

User Movement
↓
Face Position Detection
↓
Screen Center Comparison
↓
Horizontal Rotation Command
↓
Servo Motor Control
↓
User Tracking

---

## 7. Posture Change Mode

사용자의 자세가 변화하는 경우 높이 및 각도 조절이 가능하도록 구성하였습니다.

Posture Change
↓
User Posture Recognition
↓
Target Viewing Position Calculation
↓
Height Adjustment
↓
Angle Adjustment
↓
Viewing Position Update

---

## 8. Position Memory Mode

사용자가 자주 사용하는 위치를 저장하고 해당 위치로 자동 복귀할 수 있도록 위치 메모리 기능을 고려하였습니다.

Saved Position Selection
↓
Target Position Load
↓
Current Position Check
↓
Movement Path Check
↓
Actuator Control
↓
Target Position

---

## 9. Obstacle Detection

자동 이동 과정에서 주변 물체와 충돌하지 않도록 근접센서 기반 장애물 감지 기능을 적용하도록 설계하였습니다.

Movement Path
↓
Obstacle Detection
↓
Obstacle Check
↓
Movement Restriction or Path Adjustment
↓
Motion Control

---

## 10. Controlled Motion Units

제어 대상 구동부는 다음과 같습니다.

- Height Adjustment Unit
- Horizontal Rotation Unit
- Distance Adjustment Unit
- Angle Adjustment Unit

각 구동부를 독립적으로 제어하여 사용자 위치에 적합한 모니터 위치를 구성하는 것을 목표로 하였습니다.

---

## 11. System Integration

본 프로젝트에서는 기계 구동부와 사용자 인식, 위치 센서 및 제어부를 하나의 시스템으로 연계하는 구조를 설계하였습니다.

AI User Recognition
+
Position Feedback
+
Obstacle Detection
↓
Control Unit
↓
Multi-Axis Motion System
↓
Monitor Position Adjustment

본 문서는 시스템의 제어 개념을 설명하기 위한 자료이며, 상세 제어 알고리즘 및 비공개 설계정보는 포함하지 않습니다.