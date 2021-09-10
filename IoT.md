# IoT

# `08.23`

ROS(Robot Operating System)

요즘은 스마트홈은 서버에 연결되어 원격으로 제어하거나 타이머를 맞춰놓는 간단한 형태가 아니라

집에서 로봇이 돌아다니는 형태로 바뀜

→ 그곳에 들어가는 SW의 개발을 도와주는 역할

# ROS

- 메타 운영체제라고 한다. OS 위에 설치하고 OS에 있는 기능들을 이용하여 스케줄링, 감시, 에러처리 등을 처리한다. → 이러한 컨셉을 미들웨어, 소프트웨어 프레임워크라고 한다.
- 새로운 OS를 배우는게 아니라 ROS에서 만들어놓은 Client Library를 이용해서 원하는 기능을 수행하는 Node(프로그램)을 만드는 것
- 우리는 ROS2를 사용할 거임

TCP/UDP → DDS(Data Distribution Service) :  네트워크에 존재하는 통신 객체들을 자동으로 검색하고 데이터의 연관성에 따라 선택적으로 연결을 수행 → 다수의 로봇, 장치를 연결하기에 효과적이다.

기존은 Master라는 노드가 직접 연결을 해줬다면 ROS2는 Master가 따로 존재하지 않고 분산되어 처리, Master가 죽어서 모든 시스템이 마비되는 걱정을 하지 않아도 됨

<br>

<br>

# `09.09`

# **지능형 사물 인터넷 AIoT**

## ASIC

GPU 기반으로 칩으로 AI 처리를 하는 것

트레이닝은 임베디드 작업에서도 어렵다.

ASIC → TPU, NPU 등에서 가능하다.

TPU ↔ 클라우드

- 대표적인 서비스 AWS
- 임베디드는 복합한 연산이 불가능하지만 TPU 나오면서 다시 각광을 받고 있다.
- 중앙화된 서버에서 연산을 하는 것이 아니라 디바이스에서 연산을 할 수 있다.

## 엣지 디바이스 추론 장점

- Real Time 에 가까운 빠른 응답 처리
- 상대적으로 높은 보안을 보장
- 클라우드 GPU 서버 비용과 시간 감소
- 고도로 지능화된 제품 개발이 용이

## 임베디드 CPU 기반 AI 영상처리 단점

- 저사양 CPU 의 저속 객체 감지를 수행

- 느린 속도로 인해 실시간 처리 불가능

- CPU 부하로 자율주행에도 영향을 줄 수 있음

  ex) teachable machine

## Google Coral USB Acc

- NPU 탑재되어서 나오는 사용 프로덕트도 있다.

  https://coral.ai/products/

## Open Edge Computing Products

- NDIVIA - Jetson

  https://www.nvidia.com/ko-kr/autonomous-machines/jetson-store/

- Google - Coral

## Closed Edge Computing Products

- TESLA → AI Day
- D1 칩 공개
