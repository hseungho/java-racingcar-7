# 자동차 경주 게임
Course 2 - `java-racingcar-precourse`

## 요구사항 정의서
**초간단 자동차 경주 게임을 구현한다.**

- 주어진 횟수 동안 n대의 자동차는 전진 또는 멈출 수 있다.
- 각 자동차에 이름을 부여할 수 있다. 전진하는 자동차를 출력할 때 자동차 이름을 같이 출력한다.
- 자동차 이름은 쉼표(,)를 기준으로 구분하며 이름은 5자 이하만 가능하다.
- 사용자는 몇 번의 이동을 할 것인지를 입력할 수 있어야 한다.
- 전진하는 조건은 0에서 9 사이에서 무작위 값을 구한 후 무작위 값이 4 이상일 경우이다.
- 자동차 경주 게임을 완료한 후 누가 우승했는지를 알려준다. 우승자는 한 명 이상일 수 있다.
- 우승자가 여러 명일 경우 쉼표(,)를 이용하여 구분한다.
- 사용자가 잘못된 값을 입력할 경우 `IllegalArgumentException`을 발생시킨 후 애플리케이션은 종료되어야 한다.

### 입출력 요구 사항

#### 입력

- 경주할 자동차 이름(이름은 쉼표(,) 기준으로 구분)
```
pobi,woni,jun
```
- 시도할 횟수
```
5
```

#### 출력

- 차수별 실행 결과
```
pobi : --
woni : ----
jun : ---
```

- 단독 우승자 안내 문구
```
최종 우승자 : pobi
```
- 공동 우승자 안내 문구
```
최종 우승자 : pobi, jun
```

#### 실행 결과 예시

```
경주할 자동차 이름을 입력하세요.(이름은 쉼표(,) 기준으로 구분)
pobi,woni,jun
시도할 횟수는 몇 회인가요?
5

실행 결과
pobi : -
woni :
jun : -

pobi : --
woni : -
jun : --

pobi : ---
woni : --
jun : ---

pobi : ----
woni : ---
jun : ----

pobi : -----
woni : ----
jun : -----

최종 우승자 : pobi, jun
```

## 기능 명세서
|        기능명         |                                  설명                                  |                                               정책                                                |             추가 정책              |
|:------------------:|:--------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------:|:------------------------------:|
|     자동차 이름 입력      |                        사용자가 자동차 이름(들)을 입력합니다.                        | - N개의 자동차 이름을 입력할 수 있습니다. <br> - 자동차 이름은 `,`를 기준으로 구분할 수 있다. <br> - 자동차 이름은 `5자 이하`로만 입력할 수 있다. | - 자동차 이름은 `최대 10개`까지만 입력가능합니다. |
|      이동횟수 입력       | 사용자가 경주 게임 자동차의 이동횟수를 입력합니다. <br> 이동횟수란 경주게임에서 전진/정지를 진행하는 횟수를 말합니다. |                                                -                                                | - 이동횟수는 최대 `20`까지만 입력할 수 있습니다. |
|       자동차 생성       |                    사용자가 입력한 값을 이름으로 한 자동차를 생성합니다.                    |                              - 사용자가 입력한 자동차 이름의 수 만큼만 자동차를 생성합니다.                               |               -                |
| 게임 중 자동차 무작위 전진/멈춤 |     경주게임 시작 이후 회차마다 각 자동차마다 0~9 사이의 무작위 값이 4 이상이 나온 자동차는 전진합니다.      |                                                -                                                |               -                |
| 게임 중 이동 회차당 현황 출력  |                경주게임 시작 이후 회차마다 자동차가 이동한 결과를 모두 출력합니다.                |                                   - 자동차가 전진을 할 경우 `-`가 추가됩니다.                                   |               -                |
|   게임 종료 이후 결과 출력   |         사용자가 입력한 이동횟수만큼 회차가 진행된 이후 경주의 최종 우승 자동차 이름을 출력합니다.          |                - 최종 우승자는 한 명 이상이 될 수 있습니다. <br> - 우승자가 여러 명일 경우 `,`를 이용하여 구분합니다.                |               -                |