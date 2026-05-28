# Binance 선물 거래소

## 📌 한 줄 통찰
> 글로벌 최대 유동성, 선물 수수료 Maker 0.02% / Taker 0.04%, API WebSocket으로 실시간 데이터 수신

## 기본 정보
- 유형: 선물 (USDT-M Perpetual)
- 레버리지: 최대 125배
- 수수료: Maker 0.02% / Taker 0.04% (VIP 레벨별 상이)

## API 연동
- REST API: 주문, 계좌 조회
- WebSocket: 실시간 캔들, 체결, 호가창
- API 엔드포인트: https://fapi.binance.com (REST), wss://fstream.binance.com (WebSocket)
- 라이브러리: python-binance, ccxt

## 주요 엔드포인트
- 캔들 데이터: /fapi/v1/klines (REST), <symbol>@kline_<interval> (WS)
- 주문 실행: /fapi/v1/order (POST)
- 계좌 잔고: /fapi/v1/account 또는 /fapi/v1/balance

## 리스크 관리 기능
- 스톱로스 주문: STOP_MARKET
- 테이크프로핏: TAKE_PROFIT_MARKET
- 포지션 모드: 단방향 / 헤지 모드
- 격리(Isolated) vs 교차(Cross) 마진 모드 설정 필수

## 주의사항
- 청산 가격 계산 방법: 유지 증거금(Maintenance Margin) 비율에 따른 강제 청산 로직 이해 (Mark Price 기준)
- 펀딩비: 8시간마다 발생하는 펀딩비(Funding Rate) 확인 및 포지션 유지 비용 계산
