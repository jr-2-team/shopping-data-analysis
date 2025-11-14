# 온라인 쇼핑 저매출 지역 타깃 마케팅 전략
데이터 분석 프로젝트 | 미국 소비자들의 쇼핑 행동 패턴 분석을 중심으로

## 0. 프로젝트 개요
<img width="400" height="333" alt="image" src="https://github.com/user-attachments/assets/2b7d2b94-4221-4bc8-9e5f-e724a78f1ad0" />
<img width="512" height="220" alt="image" src="https://github.com/user-attachments/assets/a1c7db9a-c5cb-41fe-bb31-6e9098734f58" />

비대면 소비가 일상화되면서 **온라인 패션 시장은 전례 없는 속도로 성장하고 있다.**
모바일 쇼핑의 보편화와 SNS 중심의 패션 트렌드 확산은 소비자들에게 브랜드 간의 경계 없는 비교와 즉각적인 구매를 가능하게 만들었다.
이제 소비자들은 오프라인 매장을 방문하기보다 온라인 플랫폼에서 **다양한 브랜드와 스타일을 탐색하고, 자신에게 어울리는 상품을 직접 선택**하는 데 익숙해졌다.
특히 **MZ세대를 중심으로 개성과 취향을 중시하는 소비 문화**가 확산되면서, 단순히 옷을 구매하는 행위가 아닌 ‘자신을 표현하는 수단’ 으로서의 패션이 부각되고 있다.
이러한 변화 속에서 ‘색상’은 개인의 정체성과 감성을 드러내는 핵심 요소로 작용하며, 소비자들의 구매 결정 과정에서 **브랜드나 가격만큼 중요한 요인**으로 자리 잡고 있다.
즉, 현대의 온라인 쇼핑 시장에서 색상은 단순한 시각적 속성을 넘어 **소비자 심리와 행동을 이끄는 핵심 변수**로 작동하고 있는 것이다.

## 1. 프로젝트 목적
본 프로젝트의 목적은 **미국 내 지역별 온라인 패션 소비 데이터를 분석**하여**,
지역 간 매출 편차의 원인을 규명**하고 **효율적인 지역 맞춤형 마케팅 전략을 제안하는 것**이다.
이를 위해 각 지역(동부·중부·서부)의 총매출과 소비 특성을 비교하고,
그중 상대적으로 매출이 높은 지역 내에서도 판매 실적이 저조한 거점을 선별하여
매출 감소 요인을 심층적으로 분석한다.
이 과정에서 **색상·계절·연령대별 선호도, 할인 및 구독 여부, 구매 주기** 등
소비자 쇼핑 행동 요인을 기반으로 고려하여,
지역별 소비 패턴의 차이를 정량적으로 파악하고자 한다.
최종적으로는 이러한 분석 결과를 바탕으로
- 저매출 지역의 소비자 성향에 맞춘 상품 색상 및 시즌 전략,
- 프로모션 및 구독 프로그램 개선 방향,
- 재고 및 마케팅 자원 효율화 방안

등을 제시함으로써,
전체 온라인 패션 시장 내 **지역별 매출 균형과 성장 가능성 극대화**를 목표로 한다.


## 2. 데이터 기본 정보
- 데이터 출처 : Kaggle - shopping_behaviour
- 데이터 구성 : 총 18개 컬럼, 3900개 행
- 총 데이터 수 : 3900개
- 컬럼 수 : 18개
- 주요 컬럼 : 'Location', 'Color', 'Season', 'Age' 등

## 3. 기술 통계 요약
- 수치형 변수
<img width="673" height="248" alt="image" src="https://github.com/user-attachments/assets/0bbe615d-7ad3-40eb-a85e-de6b27ec3fa2" />

- 범주형 변수
<img width="1262" height="121" alt="image" src="https://github.com/user-attachments/assets/d160c0a5-204b-44ce-baf6-eeb4b010814c" />


## 4. 결측치 및 이상치 탐색
- 결측치 : 없음
- 이상치 : 없음

## 5. 데이터 전처리
| **1. 새로운 변수 생성** |
- 고객의 거주지(Location)를 기반으로 `동부(East)`, `중부(Central)`, `서부(West)`로 구분하는 `Region` 변수 생성
- 상품명(Item Purchased)을 기준으로 의류 및 패션 제품을 `상의`, `하의`, `원피스`, `신발`, `가방`, `액세서리`, `기타`로 재분류하는 `Item Category (Refined)` 변수 생성

| **2. 그룹핑 처리 및 범주 단순화** |
- `Age` 변수를 구간별로 묶어 국가에서 지정한 표준 연령대로 `18~34` 청년층, `35~49` 중년층, `50~64` 장년층, `65~` 노년층 의 연령대를 생성
- `Review Rating`을 1점대~5점대로 구간화하여 고객 만족도 분포 분석을 용이하게 하였음.

| **3. 편향 개선** |
- 지역별 및 연령대별 데이터 불균형 완화를 위해 각 그룹별 동일 인원 수(예: 65명, 1000명)로 샘플링 수행<br>- 표본 간 편차를 최소화하여 통계적 신뢰도 확보

## 6. 변수 간 관계 분석

> 성별, 구매항목에 따른 지출금액 평균
<img width="1345" height="145" alt="image" src="https://github.com/user-attachments/assets/175d83ea-7a82-4cb9-aa71-b1f91674fb52" />
<img width="1179" height="774" alt="image" src="https://github.com/user-attachments/assets/410b6529-162b-4e4f-8d7b-ce06fe0631a5" />

> 연령대별 색상 선호도 및 구매 항목 상위 5가지
<img width="798" height="425" alt="image" src="https://github.com/user-attachments/assets/2bcb80a6-e88c-4254-928c-1b83c2afa12f" />

> 카테고리별 색상 선호도
<img width="980" height="578" alt="image" src="https://github.com/user-attachments/assets/4ced4aac-d768-4978-8a9a-b2b31f1c7309" />


### A. 연령대별로 모집단 분포를 확인한 뒤, 국가에서 지정한 표준 연령별로 모집단 분포를 나눔.
<img width="699" height="474" alt="image" src="https://github.com/user-attachments/assets/a282f83e-9bfa-457c-8683-d0cc2658c168" />

> 연령을 10개 단위로 나누어 확인한 모집단 분포

<img width="699" height="474" alt="image" src="https://github.com/user-attachments/assets/e444da63-5c42-49ab-aad6-ad06d6b61e73" />

> 전체적인 분포를 고려하여 연령을 4개층으로 분리
- 청년층(18~34세)
- 중년층(35~49세)
- 장년층(50~64세)
- 노년층(65세 이상~)

### B. 미국 지역별(동부/중부/서부) 인구 밀집도 및 인구 수를 확인하고, 모집단 수를 동등하게 맞춘 기준의 총 매출을 확인
<img width="763" height="314" alt="image" src="https://github.com/user-attachments/assets/72fa93c6-c620-4dfe-b1a3-6c8ad60d3b79" />
> 지역별 인구 밀집도
<img width="793" height="600" alt="image" src="https://github.com/user-attachments/assets/de790ce3-4bb4-4ea8-874a-3d980ea7f862" />
> 동일한 모집단 수 조건에서 지역별 총 매출 확인

### C. 매출이 가장 많은 서부 지역 중, 세부 지역 (주) 별로 분리한 기준 매출 하위 3개 지역 추출
<img width="1582" height="690" alt="image" src="https://github.com/user-attachments/assets/519b3b16-960e-4b25-b4e5-c30d5f029b74" />

### D. 하위 3개 지역의 매출 상승 방안을 고려하기 위해 다양한 관점에서 진행한 데이터/상관관계 분석
<img width="1990" height="1475" alt="image" src="https://github.com/user-attachments/assets/2b37c414-39ef-459a-9dee-a46157063141" />
<img width="1990" height="691" alt="image" src="https://github.com/user-attachments/assets/b6bfbda1-2fac-461c-a3ad-efc9433e529c" />


## 7. 요약 및 인사이트 도출

> 요약

주요 구매층 | 남성의 구매 비중이 여성의 약 2배 수준.	남성 타깃 중심의 마케팅 전략 필요
구독 여부 | 구독 여부(YES/NO)는 여성 고객에게서는 전혀 나타나지 않았으며, 남성 고객에서만 확인되어 성별에 따른 명확한 이용 행태 차이를 보여줌
연령대 분포	| 18~34, 35~39세`대(청·중년층)가 핵심 소비층
주요 카테고리	| '의류' 가 가장 높은 구매율을 차지함
변수 간 관계 기준에 따른 만족도	분포 |
- 할인 고객보다 비할인 고객의 구매금액이 높음
- 배송 방법은 무료배송, 표준배송이 평점 참여도 면에서 가장 많았으나, 무료배송이라고 하여 만족도가 무조건 높은 것은 아님.
이전 구매 수 분석에 따른 재구매율 예측 | 여성에 비해 남성의 이전 구매 수가 비교적 높은 편이었고,
남성의 경우 '주얼리', 여성의 경우 '반바지' 에 대한 이전 구매 수가 높음.


> 결론
서부 지역의 청년 남성을 주요 타겟으로, 의류·악세사리 중심의 트렌디한 상품군을 시즌별로 전개하고
색상·가격 전략을 세분화한다면, 단기적으로 지역 매출을 회복하고 장기적으로 브랜드 충성도를 확보할 수 있다.

