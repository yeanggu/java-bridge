- 비즈니스 로직 흐름
    - Application : 프로그램 시작
    - BridgeController : 비즈니스 로직 흐름 관리
    - BridgeService : 비즈니스 로직 흐름 정의
      - InputView : 재시작 여부, 이동할 칸, 다리의 길이 입력
      - OutputView : 결과 출력
    - BridgeGame : 다리 건너기 게임을 관리
    - BridgeMoving : 다리 건너기 위한 조건 정의
    - BridgeMaker : 다리의 길이를 입력받아서 다리를 생성
      - BridgeNUmberGenerator : 랜덤 값 추출
      - BridgeRandomNumberGenerator : 0,1 중 랜덤 값 추출
1. 다리의 길이 입력 기능
    - 빈 값이 입력되었는지 확인하기
    - 숫자인지 아닌지 확인하기
    - 입력한 숫자가 3 이상 20 이하의 숫자인지 검사하기
    - 잘못 입력시 반복 입력요구
2. 다리 길이에 따른 랜덤 List<String> 생성
    - 위 칸을 건널 수 있는 경우 U, 아래 칸을 건널 수 있는 경우 D값으로 나타낸다.
    - 무작위 값이 0인 경우 아래 칸, 1인 경우 위 칸이 건널 수 있는 칸이 된다.
3. 사용자가 이동할 칸을 입력하는 기능
    - U(위 칸)와 D(아래 칸) 둘 중 하나만 입력
    - 잘못 입력시 반복 입력요구
4. 게임 재시작/종료 여부 입력 기능
    - R(재시작)과 Q(종료) 중 하나의 문자를 입력
    - 잘못 입력시 반복 입력요구
5. 맵 출력하는 기능
    - "[ O |   ]” - UpList 출력
    - ”[   | O ]" - DownList 출력
6. 각종 message 기능 구현
    - 게임 시작 : "다리 건너기 게임을 시작합니다."
    - 다리 길이 입력 : "다리의 길이를 입력해주세요."
    - 이동할 칸 입력 : "이동할 칸을 선택해주세요. (위: U, 아래: D)"
    - 게임 재시작 여부 입력 : "게임을 다시 시도할지 여부를 입력해주세요. (재시도: R, 종료: Q)"
    - 최종 결과 출력 :
      ”최종 게임 결과”
      ”[ O |   |   ]”
      ”[   | O | O ]”

   ”게임 성공 여부: 성공”
   ”총 시도한 횟수: 2”
    - 예외 상황 :
      다리길이 숫자 입력x : “[ERROR] 다리 길이는 숫자여야 합니다.”
      다리길이 범위 벗어남 : “[ERROR] 다리 길이는 3부터 20 사이의 숫자여야 합니다.”
7. 총 시도한 횟수 기능 구현