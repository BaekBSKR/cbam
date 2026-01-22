# CBAM (Convolutional Block Attention Module) Code Review

## 1. 코드 출처 및 개요
- 논문: CBAM: Convolutional Block Attention Module
- 목적: Channel + Spatial Attention을 순차적으로 적용

## 2. 전체 구조 요약
CBAM = ChannelGate → SpatialGate

## 3. 모듈별 코드 리뷰

### 3.1 BasicConv
- Conv + BN + ReLU를 모듈화

### 3.2 ChannelGate
- AvgPool / MaxPool 기반 채널 어텐션
- MLP 구조: C → C/r → C

### 3.3 SpatialGate
- ChannelPool(max, mean) → 7×7 Conv
- spatial attention의 receptive field 확보 목적
