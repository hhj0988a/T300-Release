# T300-SW Release-v1.0.0 Note(2020-06-19)
- Highlights
- Add function
- BugFix

## Highlights
 1. T300 Install 간 요청 사항 추가 및 버그 수정
 
## AddFunction
 
   - [TCM]() Carrier found Alarm TimeOut 기능 추가  
   - [TCM]() Function 內 TimeOut Spec을  코드 외부에서 가능 하도록 수정  
   - [TCM]() TCM을 다시 시작 할 경우 서로 다른 TCM 간의 Hand Off 데이터 존재 여부 검사 코드 추가  
   - [TCM]() SenSor Alarm 검사 코드 기능 일부 개선  
   - [TCM]() OutPutPort에서 Carrier가 대기 중 센서2, 3번 모두 미감지될 경우에 E84 알람 발생(__기존에는 2번만 미감지되어도 알람__)  
   - [TCM]() Alarm 발생 시 로그 시에 서버 시간이 표시 되도록 변경함  
   - [TCM]() 이송 시퀀스 동작 쓰레드가 Redis에 데이터를 비동기로 업데이트 하도록 변경
   - [GUI]() 메뉴얼 구동 시 Zone을 벗어나지 않도록 LD 센서 1번 Limit 기능 추가  
   - [GUI]() TCM 과 Redis 서버의 통신이 끊어질 경우 팝업 기능 추가  
   - [GUI]() Tower Lamp 기능 추가   
      * YELLOW 동작 추가  
      __BLINK__ : TSC 상태 AUTO And Control 상태 ONLINE And Communication 상태 ENABLE  
      __STEADY__ : Maint 상태 즉, TSC 상태가 AUTO 가 아닌 상태 Or Control 상태 OFFLINE Or Communication 상태 DISABLE  
   - [GUI]() ZoneOperator 기능 중 Task Reserved 기능 추가-실수로 Task Reserve를 취소 할 경우 다시 Reserve 하는 기능 추가  
   - [HIM]() OutPut 시퀀스 중 __RFID__ Mismatch 발생 시 __OldCarrierID__ 를 추가로 올려 주도록 수정  
   - [HIM]() Event 보고 삭제 - TSC_INIT
   - [HIM]() Event 보고 - 장비 상태 변경 시200ms 딜레이 추가
   - [HIM]() S2F33 에서 전체 삭제 시 __Report_ID Link__ 데이터도 삭제  
   
   
## BugFix 
   - [GUI]() GUI 시작 시에 실제 정보와 불일치 현상 개선  
   - [GUI]() __TaskTracking__ 중에 __TaskCompleted__ 되면 GUI가 먹통되는 문제 수정  
   - [TCM]() __QS TURN__ 시퀀스 중 __TURN__ 하기 전에 해당 __QS Zone_에 대한 __Task__ 점유 여부 검사하도록 수정  
   - [TCM]() __QS TURN__ 시퀀스 중 QS 방향이 Carrier가 진행 하려는 방향과 일치되는 경우 아무 작업하지 않고 시퀀스 종료  
   - [TCM]() TCM 간 Carrier Handoff시 이동거리 계산을 Carrier를 넘겨주는 TCM이 계산하여 Carrier를 넘겨받는 TCM에게 사용하도록 함
   
  
_Copyright by SEMI-TS SW TEAM 2020.06.19_