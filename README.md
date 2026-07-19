# Kotlin 금융 백엔드 릴리스 리스크 스프린트

[![validate-site](https://github.com/ngsk2784-lab/kotlin-finance-risk-sprint/actions/workflows/validate.yml/badge.svg)](https://github.com/ngsk2784-lab/kotlin-finance-risk-sprint/actions/workflows/validate.yml)

Kotlin/Spring 금융 백엔드 한 서비스를 대상으로, 배포 전에 복원력과 민감정보 취급 위험 후보를 빠르게 정리하는 48시간 정적 프리플라이트 서비스의 공개 포트폴리오입니다.

- 라이브 사이트: https://kotlin-finance-risk-sprint.vercel.app
- 서비스 대가: KRW 1,100,000. 세금·원천징수·증빙은 양측의 실제 요건에 따라 SOW에서 확정
- 범위: 서비스 1개, 검사 대상 Kotlin 소스 최대 30,000 LoC
- 기산점: SOW 승인·결제·권한 있는 접근·서면 범위·리미디에이션 슬롯 결정 규칙·비프로덕션 빌드/테스트 전제 확인 후
- 산출물: 전체 기계 후보 `findings.json`, 최대 30개 후보의 사람 검토가 담긴 개발자 보고서, 실행 추적 문서, 1개 remediation slot, 재검사 또는 구현 계획, 30분 결과 리뷰

## 검사하는 7개 신호

1. 외부 호출 타임아웃
2. 재시도·백오프
3. 서킷브레이커
4. 커넥션 풀·리소스 상한
5. 하드코딩된 시크릿·키
6. 카드·계좌·주민번호 등 민감 필드의 평문 취급
7. 접근·거래 로그

검사는 결정론적 파일 단위 휴리스틱과 코드 맥락 검토를 결합합니다. 전체 기계 후보를 기록하고, Critical 우선으로 중복 제거한 최대 30개 후보를 사람이 검토합니다. 30개 이하면 전부 검토하고 초과분은 미검토 기계 후보로 구분합니다. 특히 재시도·서킷브레이커 검사는 WebClient, RestTemplate, `@FeignClient` 중심의 제한된 패턴만 다룹니다. 오탐과 미탐이 가능하며, 결과가 0건이어도 안전성이나 규정 준수를 증명하지 않습니다.

## 포함하지 않는 범위

이 서비스는 법률 자문, 침투 테스트, CVE·의존성 스캔, 런타임·부하 테스트, 전체 보안 감사, 규정 전체 항목 점검, 컴플라이언스 인증 또는 자동 수정을 제공하지 않습니다.

## 문의

무료 샘플은 검사 승인 권한과 고정 커밋을 확인한 공개 저장소에서 최대 20개 소스 파일 또는 5,000 LoC 중 먼저 도달하는 범위에 실행합니다. 산출물은 1쪽 이내 요약과 대표 후보 최대 3건이며 리미디에이션 슬롯은 포함되지 않습니다. [무료 샘플 요청 Issue](https://github.com/ngsk2784-lab/kotlin-finance-risk-sprint/issues/new?template=free-sample.yml)를 열거나 [ngsk2784@gmail.com](mailto:ngsk2784@gmail.com)으로 범위를 요청할 수 있습니다. 이메일이나 공개 Issue에 소스 코드, 토큰, 비밀번호, 실제 고객·금융 데이터를 첨부하지 마십시오.
