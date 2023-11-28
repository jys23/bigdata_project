# bigdata_project
-----------------------------------------
## NHL 선수들 중 '돈 값'하는 선수는 몇이나 될까?

#### 주제선정
NHL(북미 아이스하키 리그)은 샐러리캡이 적용된 리그로, 모든 팀이 같은 돈으로 선수 로스터를 꾸려야 합니다.  
따라서 가성비 좋은 선수들을 많이 확보하는 것이 곧 팀의 성적과 직결됩니다.  
이번 프로젝트에서는 선수별로 연봉 대비 퍼포먼스를 계산하여, 누가 팀에 득이 되고 실이 되는지를 판단해보겠습니다.


#### 데이터 수집
* 선수별 스탯(출전경기수, 골, 어시스트, 슛팅횟수 등등) 데이터
  * 수집방법: NHL 공식 사이트(https://www.nhl.com/stats/skaters) 에서 제공
  * 수집범위: NHL에 샐러리캡이 적용된 2005시즌 이후부터 2022시즌까지
* 선수별 연봉 데이터
  * 수집방법: 'capfriendly'라는 사이트(https://www.capfriendly.com/browse/active/) 에서 크롤링
  * 수집범위: 2005시즌~2022시즌
* 시즌별 각 팀의 총 연봉 상한선 데이터
  * 수집방법: 'capfriendly'라는 사이트(https://www.capfriendly.com/salary-cap) 에서 크롤링
  * 수집범위: 전체


#### 프로젝트 개요

1. 스탯데이터와 연봉데이터의 전처리를 진행한다. (예를 들어, 2005시즌 연봉 10억은 2022시즌 기준 약 21억 1500만원으로 환산된다.)  
    [[데이터크롤링.md](https://github.com/jys23/bigdata_project/blob/main/데이터크롤링.md)]  
2. 각 선수의 스탯데이터와 연봉데이터를 병합한다.  
    [[스탯연봉병합.md](https://github.com/jys23/bigdata_project/blob/main/스탯연봉병합.md)]  
3. 스탯데이터를 feature로, 연봉데이터를 target으로 머신러닝(지도학습)을 진행하여 스탯데이터가 입력되면 그에 상응하는 연봉을 출력하는 모델을 생성한다.  
    [[머신러닝.md](https://github.com/jys23/bigdata_project/blob/main/머신러닝.md)]  
4. 생성된 모델을 이용하여 예상연봉을 출력하고, 예상연봉을 실제연봉으로 나누어 각 선수별로 퍼포먼스 점수를 매긴다.  
    [[퍼포먼스점수계산.md](https://github.com/jys23/bigdata_project/blob/main/퍼포먼스점수계산.md)]  
5. 각 팀별로 가성비 좋은 선수가 얼마나 있는지, 팀성적과 연관관계가 있는지 시각화하여 분석한다.  
    [[데이터시각화.md](https://github.com/jys23/bigdata_project/blob/main/데이터시각화.md)]  


#### 결과 예상

* 성적이 좋지 않은 팀은, 가성비 안좋은 선수들이 많이 있을 것이다.
* 팬들 사이에서 소위 'Overpay' 되었다고 평가받는 선수들은 점수도 안좋게 나올 것이다.
