  # 📦 물류센터 상품 자동 검사 시스템

## 📌 프로젝트 개요

이 프로젝트는 물류센터 내 상품 검수 단계에서 발생하는 **병목현상과 인력 의존 문제**를 해결하기 위해,  
**YOLOv11 기반 객체 인식 모델**을 활용한 **AI 자동 검사 시스템**을 구현한 프로젝트입니다.

YOLO 모델을 Fine-Tuning하여 다양한 상품을 자동 인식하고,  
실제 상품 분류와 검수 과정을 대체할 수 있는 **실시간 AI 비전 솔루션**을 설계하였습니다.

---

## 🧠 문제 정의

- 전체 물류 공정 중 **상품 검수 단계의 병목이 가장 심각**
- **수작업 검수**는 시간 소요가 크고 **오류율도 높음**
- 상품 종류가 다양해 사람이 분류하기 어려움

> ✅ **AI 기반 다중 객체 인식**으로 빠르고 정확한 상품 분류 및 검수 자동화 필요

---

## 🎯 프로젝트 목표

- YOLOv11을 활용한 **다중 객체 인식 모델 학습 및 최적화**
- 생활물류 상품 26종 자동 분류 및 시각화
- 다양한 모델 실험을 통해 **정확도와 처리 속도 균형 최적화**

---

## 🖼️ 시스템 구성

[Vision 카메라]<br>
↓<br>
[YOLOv11 객체 검출 (Fine-Tuning)]<br>
↓<br>
[상품 클래스 분류 및 바운딩 박스 표시]<br>
↓<br>
[시각화 및 결과 출력]<br>
<br>

- 실시간 영상 입력 기반
- 검출된 상품의 위치, 클래스, 확률을 표시
- 후처리를 통해 검수 결과로 활용 가능

---

## 🧪 YOLOv11 모델 성능 요약

| Metric        | YOLOv11_n | YOLOv11_s | YOLOv11_m | YOLOv11_l |
|---------------|------------|------------|------------|------------|
| **mAP50**     | 0.964      | 0.965      | 0.964      | 0.963      |
| **mAP50-95**  | 0.879      | 0.890      | 0.873      | 0.883      |
| **Precision** | 0.957      | 0.956      | 0.953      | 0.957      |
| **Recall**    | 0.945      | 0.949      | 0.940      | 0.940      |
| **F1 Score**  | 0.951      | 0.952      | 0.946      | 0.949      |
| **Mean IoU**  | 0.951      | 0.952      | 0.946      | 0.949      |
| **FPS**       | 191.53     | 72.84      | 26.04      | 20.79      |

> 📌 YOLOv11_s 모델이 **정확도와 처리속도 측면에서 가장 균형이 우수**함  
> YOLOv11_n은 **FPS 191.53**으로 초고속 실시간 처리 가능

---

## 📁 데이터셋 정보

- **총 이미지 수**: 22,586장
- **데이터 경로**:
  - `train`: `/content/drive/MyDrive/Bigproject/data_food/images/train`
  - `val`: `/content/drive/MyDrive/Bigproject/data_food/images/val`
  - `test`: `/content/drive/MyDrive/Bigproject/data_food/images/test`
- **데이터 구성 방식**:
  - Roboflow Universe에서 수집한 **생활물류 오픈 데이터**
  - 물류센터 환경을 반영한 **직접 촬영한 이미지 병합**
- **클래스 수**: 총 26개  
  - `bread`, `snack`, `coffee`, `juice`, `noodle`, `seasoning`, `shampoo`,  
    `soap`, `bodywash`, `moisturizer`, `detergent`, `toothpaste`, `tata_salt`,  
    `cheese`, `egg`, `milk`, `meat`, `sausages`, `beverage`, `canned_food`,  
    `miscellaneous_item`, `apple`, `banana`, `tomato`, `cucumber`, `carrot`
---

## 🛠️ 기술 스택

| 항목       | 내용 |
|------------|------|
| Language   | Python |
| 모델       | YOLOv11 (Ultralytics 기반) |
| 프레임워크 | OpenCV, NumPy |
| 데이터셋   | Roboflow + Custom Image |
| 개발 환경  | Google Colab, VS Code, IntelliJ |

---
<!--
## ▶️ 실행 방법

```bash
# 1. 필수 패키지 설치
pip install ultralytics opencv-python numpy

# 2. 모델 학습
yolo task=detect mode=train model=yolov8n.pt data=data.yaml epochs=50 imgsz=640

# 3. 상품 검출 실행
yolo task=detect mode=predict model=best.pt source=./test_images

- YOLOv11 기반 Fine-Tuning 모델 정확도 **95% 이상**
- 다중 상품 실시간 검출 성공
- **MFC(물류 풀필먼트 센터)** 적용 가능성 입증
- 검수 자동화로 **병목 해소 및 인건비 절감** 기대

---
-->
