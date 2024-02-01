# 아키텍처 특성의 측정 및 거버넌스

아키텍처 특성을 구체적으로 정의하고 거버넌스 메커니즘을 구축하는 방법을 살펴보는 장

## 아키텍처 특성 측정

- 아키텍처 특성을 더 잘게 나누어 분석하고 객관적으로 정의할 수 있는 측정 가능한 특성을 밝혀내야 한다
- 운영적 측정
    - 성능
    - 통계 분석 결과로 얻은 정의에 기반하여 성능 수치 목표를 잡는다
- 구조적 측정
    - 내부 구조
    - 코드 복잡도는 순환 복잡도(CC)라는 메트릭을 통해 측정
    - CC = E - N + 2 (N은 노드, 코드 라인 & E는 간선, 가능한 결정)
- 프로세스 측정
    - 소프트웨어 개발 프로세스와 교차하는 아키텍처 특성
    - 민첩성 → 시험성 + 배포성으로 나눌 수 있는 아키텍처 특성
    - 시험성 : 코드 커버리지 도구로 측정, 배포성 : 배포 성공률, 배포 소요시간, 배포시 발생한 이슈 로 측정 → 객관적으로 측정 가능

## 거버넌스와 피트니스 함수

- 거버넌스 : 아키텍트가 영향력을 행사하려는 모든 소프트웨어 개발 프로세스를 포괄
- 아키텍처 피트니스 함수 : 아키텍처 특성의 객관적인 무결성을 평가하는 모든 메커니즘.
    - 수많은 도구들은 바라보는 새로운 시각.
    - 메트릭, 모니터, 단위 테스트 라이브러리, 카오스 엔지니어링
    - **순환 의존성 :** 각 컴포넌트가 다른 컴포넌트의 코드를 참조. JDepend라는 메트릭 도구를 이용한 피트니스 함수로 순환 참조 여부를 발견해서 해결할 수 있다.
    - **메인 시퀀스로부터의 거리 :** JDepend라는 메트릭 도구를 이용해 거리를 측정하여 임계치를 넘는지 여부를 판단 가능
    - 레이어 의존성을 확인하는 도구도 존재
    - 피트니스 함수를 활용해서 중요한 거버넌스 체크를 아키텍처 하부에 구체화하여 체크 리스트를 지키자