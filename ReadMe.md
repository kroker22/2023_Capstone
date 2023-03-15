# 2023_Capstone
# 팀장이 쓰는 피드백

2023 1. 10 ~ 모터 선정, 모터 드라이버선정  
모터 MD로봇의 BL9 + ENCODER 부착형 모터 32만원 
모터 드라이버 MD500S 16.6만원
중국인 한명더 들어와서 쓸 수 있는 금액 

미리 모터 사겠다고 해서 남은돈 ==> 10만원 ( 정확하게 10만원 남음)
조황교수님에게 지원 받은 돈 =====> 33만원 (모터 + 감속기 가격)
중국인 포함 5인 지원금 ==========> 50만원 
한명씩 12만 5천원 씩 학기 끝나고 분배.
대회 없이 순수 지원금 ============> 10 + 33 + 50 == > 94

육각렌치 세트             --> 4820원 
스탠맨 복스 소켓렌치 세트 --> 15900원
--20720원 

##############################################
###### 정기 발표는 매주 화요일 입니다.#########
##############################################


2023 2.1 ~ 2.9 하드웨어 부품 픽스, 설계도 작성

2023 2.10 ~ 2.16 그린 설계도 기반 simscape simulation, 부품마다 업체 찾아서 주문 할 준비 ( 비싼거 말고)

2023 2.18 ~ 2.28 하드웨어 디버깅, bldc 모터 stm으로 앵간치 돌릴줄 알아야함 

(2월 부터 3월 중순 까지는 하드웨어 수정이랑, 시뮬레이션 병행 해야함) 

# 2023. 2. 10 Feedback  ############################################################

- 베어링,샤프트,암 부분 체결하는곳 inventor 에서 다시 설계해야함
- 하우징 바깥 부분을 body1 내부에 넣고, 중간에 파이프 하나 더 박아서 하우징 두번째 부분을 따로 고정 시켜야함 
- 하우징 문제를 해결하려면 본체 가로 폭을 넓혀야 할거라고 생각됨
- 바퀴 회전축으로 부터의 아랫부분 무게와 위에 달려있는 배터리나 돌림힘의 비교가 필요함

#######################################################################################

# 2023. 2. 14 Feedback  ############################################################

- bearing ===> shaft 연결부분 1.5mm ~~~ 2.0mm로 고정 부분 넓히기
- 텐셔너 고정부분 --> Square 하지말고 원형으로 
- 바퀴부분 연결된 Shaft 에 엔코더 부착은 없는걸로 --> 엔코더 하나로 1:50, 1:3 계산 이용해서 보드로 따로 값 전달
- 파이프 --> 프로파일로 바꾸면서 용접문제, 대각선 고정 문제 해결 
- Arm 연결부분 사각형으로 만든건 ok --> 나사구멍 홀텝가공 M4
- 계단 충돌문제는 기어박스를 거꾸로 부착하면 --> ARM 길이 수정안해도됨 --> 거꾸로 붙여서 전부 해결 
- 하우징 고정은 
                커플링 - 하우징 - 암 
                                      이런 순서로 고정되어 있다.
   이런 순서에서 하우징을 고정 시키려면 
   
          커플링 - 링 - 하우징 - 링 - 암 
                                      이렇게 고정을 하면됨 
                                      
 - 조립 순서에 대해서도 생각해봐야함    
 - 조립은 우리가 다해야하는데, 프로파일로 인해서 용접 문제는 해결 되었지만 
        ARM, ARM connector, shatf, 모터 고정 부분
                                                 이부분은 직접 설계도를 줘서 만들어야험 
#######################################################################################

# 2023. 2. 21 Feedback  ############################################################

- 프로파일 대각선 연결 부분 문제 --> 대각선 프로파일에 홀가공, 바디 프로파일에 탭가공해서 T 너트 사용 체결
- 아이들러 샤프트 연결 부분 문제 --> 샤프트를 볼트처럼 가공, 내부 구멍에 나사선 생성 + 스냅링 끼워넣을 홈 파놓음 ( 아이들러 고정용) 
- 모터 토크 문제로 하단 부분 하드웨어 변경 

          Before --> 프로파일을 중간에 연결해서 모터 -- 하우징 -- 커플링  이 순서로 체결된 부분을 가이드를 사용해서 고정했음 
          
          After  --> 하우징, 커플링을 전부 없애고, 평기어를 사용 --> Body 폭을 확실히 줄일 수 있고, 전선 간섭 문제 해결 가능, 차체 폭을 줄이니까 
                                                                   자체무게가 줄어드는 효과를 노려 볼 수 있음
                                                                   
- 모터 샤프트부터, 바디 무게중심까지의 거리로 계산한 돌림힘이 모터의 출력 토크보다 쌔기 때문에, ( 배터리 + 모터 드라이버 ) 를 묶어서 한층으로 두고
  최대한 하드웨어 중심으로 내려 놓아야 돌림힘을 버틸듯 
  
- 위의 3번째 4번째 해결책으로, 평기어를 1:2 로 둔다면 모터 출력이 다시 2배가 되기때문에 무게가 기하급수적으로 늘어나지 않는다면  기어를 통해 
  문제를 해결할 수 있을것으로 보임
  
- 평기어 샤프트, 베어링 고정문제 부분만 해결이 된다면, 하우징이랑 커플링 부착 없이 하드웨어 폭을 줄일 수 있을것으로 판단.
#######################################################################################

# 2023. 2. 27 Feedback  ############################################################

- 아이들러 고정용  shaft 50mm 로 해서 양쪽에 M5 탭가공 --> M5 볼트 체결, 망치로 톡톡 쳐가면서 넣어야 함

- Arm 길이 200mm 에서 줄이는걸로 정함 --> 150mm 정도 예상 중

- Arm 쪽에 연결되는 ( 잇수가 많은 기어에 연결되는) Shaft  두께 == 10 파이 --> 8파이로 수정

- 큰 기어에 연결되는 샤프트 8파이 부분 --> 컴팩트 베어링이 빠지지 않게 튜브를 넣어서 베어링 고정 

- 모터 가이드가 현재는 1자형이지만, 하나의 큰판으로 프로파일에 고정되게함 --> 부족한 부분은 앞쪽 프로파일에 앵글브라켓으로 한번더 고정
   ( 큰 판으로 했을 때, 평기어 위치를 정하기전에는 볼트체결하는 부분과 평기어( 잇수가 큰 평기어) 가 간섭이 생겼음, 적은 잇수를 가진 평기어가 올라오면서 
   큰 잇수를 가진 평기어가 아래로 내려가가됨
   
   내려도 되는 이유는 Arm 길이를 줄이기로 했기 때문이다. 

- 큰 기어를 제대로 고정 하기 위해, Pitch Diameter를 맞춰줘야 한다. 큰 고정판에 작은 기어, 큰 기어 거리를 측정해서, 기어의 위치를 재 조정하고 
  모터 가이드에 M5 홀가공 해서 8T 로 연결부분 만들고, 5T판으로 앞쪽, 뒷쪽 베어링 고정, 뒷쪽 판 연장해서 프로파일로 고정
  
- 모터 실시간제어에 관한 공부가 다시 필요함 Real Time OS 으로 모터 Sampling 타임 부분도 같이 알아봐야함

#######################################################################################
# 2023. 3. 07 Feedback  ############################################################

- 아이들러 고정나사 구멍 크기 줄여도됨 

- 아래쪽 샤프트 고정용 링 (가장 안쪽에 있는 컴팩트 베어링) --> (가장 밖에 있는 컴펙트 베어링) 위치로 이동

- 모터 가이드 직각 부분 --> 모터 가이드 부채꼴 모양으로 다시 수정

- 타이밍 벨트 안에 
      steal -- 나일론 -- 유리섬유 
                          이런식으로 안에 선이 있음,
  우리가 원래  ( 암 길이가 200mm 일 때) S5M  --> (암 길이가 150mm 일 때) UP8M 으로 나왔는데, 둘다 가운데 유리섬유 
  이기 때문에 ( 사실 이부분 어떤 기준으로 UP8M 이 되는지 S5M 이 되는지 도저히 모르겠음)
  
  타이밍 풀리, 벨트 숫자가 의미하는 것은 Pitch간격을 나타내는 것이 였다.... 도저히 어떤 기준으로 타이밍 벨트, 풀리를 선정 하는지 모르겠으나
  
  얼마 안되는 감으로 보기엔.. 현재 우리의 문제는 200W 정격 출력을 낮은 속도로 전달해야한다는 것인데. 정격출력이 얼마의 속도 (?) 로 전달되느냐에 따라 
  타이밍 벨트의 두께가 .. 달라지는게 아닐까? 
  이부분 아무리 찾아도 대체 해답을 찾을 수 없었다...
  
- 타아밍 벨트 길이 선정 , 두개의 다이밍풀리를 감는 길이를 구해서 피치 간격으로 나눔 --> 잇수 
  잇수가 좀 많으면 아이들러로 조정해야함
#######################################################################################
# 2023. 3. 08   Feedback  ############################################################

- 아래쪽 샤프트 길이 줄임 --> 튜브 10mm 로변경해서 --> 최대한 가로 폭을 줄임 

- 본체 ( body ) 보강부분  길이 줄여서 위로 올림 

- IMU센서 최대한 회전 중심 축으로 가깝게 해서 붙여야함 --> 무게 중심에 붙여서 활용하려 했으나
  자이로센서 + 가속도계가 같이 붙어버리면 상당히 많은 노이즈가 생길것이라고 판단 --> 모터 쪽에 있는 샤프트에 붙이는게 좋다고 생각함

- 배터리 들어가는 판 2T 였는데 이부분은 충분히 두껍지 않으면 배터리가 흔들림이 생김 
  흔들림이 생기면 흔들림 자체가 외란이라 최대한 이런 부분이 없애야 함
  
- 배터리 가이드 문제는 가이드 높이가 배터리 높이보다 작게해서 볼트로 조임을 고정해야함

- 1m 정도되는 바디 높이를 어느정도 낮춰야 한다고 교수님께서 말씀하심 ( 듣고 보니 맞는 말 이라 수긍)
  요지는 어차피 바퀴 회전축기준 위쪽 ( body ) 부분의 질량으로 인한 돌림힘이   회전축기준 아랫쪽 돌림힘보다 크기만 하면 상관없음
  
#######################################################################################

- 하드웨어 설계도 가지고 업체 찾아서 부품 주문해야함

- PID 로 제어를 할것이냐 LQR 을 구현할 것이냐. LQR 로 할거면 PINKLAB 찾아서 라그랑지안 공식 확인 // 2023.2.10 -->교수님 의견은 아마 제어기없이 근야 튜닝을 해야할거라고 하심
###################################################################
# Communication
- 카메라 --> Rasberry PI --> STM32 --> DRIVER --> MOTOR 
# 2023.2.17 
카메라는 OpenCV를 이용해서 일단 진행 예정, 문제는 Rasberry PI -> STM32로 전송시 일반선 연결로는 노이즈가 많이 심함... 노이즈를 줄일 방법또는 다른 모듈을 찾아야 할지도...(with. PMG), STM32 -> DRIVER는 UART기능에서 RS485 통신기능을 이용해볼 예정(구매한 후 해봐야 알듯))

# 2023.2.20 
전송시 꺠짐 문제 해결(전압 3.3V를 STM32에 넣어주니 Ras->STM->Win 통신 완료) -> STM32에서 UART1,2 모두 사용해서 연결함, 원래는 통신속도를 Ras->stm32를 9600으로 하고 stm32->Motor를 19200으로 하려고 했으나, 일부 글자가 짤려서 나오기에 19200으로 통신속도 통일 할 예정(Double_UART 폴더 파일)

# 2023.2.21 
라즈베리파이에서 OpenCV로 카메라 켜서 일정한 부분에 경계선이 감지되면 Ras -> Win 으로 메세지를 전송하는 통신 과정 완료 (전송 과정중에서 글자가 일부 짤리는 현상이 발생했는데 이는 전송 시간 또는 전송 객체 문제일거라 생각됨) (Cam_Code -> Cam_send.py 참고)

(CAMERA --> MOTOR) 여기 까지 오기의 통신을 할 수 있느냐. 이 부분도 상당히 난이도가 높을 것이라고 생각함
- 계단 인식 밑,  평면상에서의 움직임제어 LEFT, RIGHT

- 배터리 윗쪽 가이드 설치, Battery Management system 확인 -> 모터드라이브 20A*2 + 라즈베리파이4 3A + STM32F103RB 약 1~2A 이하로 추정 ~= 24V 50A 짜리 BMS 사면 될듯함. 
- PCB로 해야하는지? , 그냥 기판으로 가야하는지  --> Noise가 얼마나 심한지 확인해봐야함?
- 

# 2023.2. 27
MDAS -> 라즈베리파이 송신 시 오류
1. 예) 183을 송신하는데 int형으로 보내짐(반대로 char로 받으면 값이 다르게 나옴)
2. 한번 보내지고 나서 연결이 끊기는 현상을 보임(MDAS 쓰레기.....)
3. 반대로 라즈베리파이에서 MDAS로 송신할때 데이터를 제대로 받기는 하나, MDAS 터미널에서 받지 못함

- 주의할것 
1. 변수타입 (MDAS에서 STM32로 제대로 받을려면 데이터타입을 int(uint32_t)로 선언해야함. 라는 개인적인 생각)
2. MAX485 연결방법 숙지 STM32 DE pin을 MAX485에 RE에 연결 TX(pin D5)->DI, RX(pin D4)->RO에 연결 
3. Molex 필요할듯 (준호가 개인적으로 구입함)
4. USB-485 커넥터 구매해서 오면 해볼예정

연결해야하는 방법

Window MDAS Program (UART2 USB->STM32) -> STM32 (UART2-> UART1) -> 
Motor Driver  (UART1 RS485-MAX485) -> 3상 연결 Motor


# 2023.2.28 (by KJH)
stm32에서 RTOS 사용방법과 역할에 대해 찾아봄
stm32에서 RTOS를 사용하기 위해선 CMSIS-RTOS API의 Free RTOS를 사용해야함(IDE에 기본으로 내장되어 있음)
기존의 RTOS를 사용하지 않는 프로그램에서는 main문을 하나만 사용한다면, RTOS를 사용한 프로그램은 main문을 독립적으로 여러개 생성하는 효과를 얻을 수 있다. 즉, 여러 개의 Task를 동시에 수행할 수 있다. 
이 때 task마다 우선순위를 설정해주어야 하는데 우선순위를 제대로 설정해 주지 않으면 충돌이 일어날 수 있음
- RTOS를 활용해 여러개의 LED를 서로 다른 주기로 깜빡이게 만드는 프로그램을 올림 확인바람

참고자료
https://blog.naver.com/0ljy0/222149773283

// SapBori -> RTOS 종류 및 사용법 in LiNux
리눅스 스케쥴링
- BATCH
- IDLE
- DeadLine
- *SCHED_Other
일반프로세스 타입, 별도 지정을 하지 않을 시에 설정 
- *SChed_FIFO((First in First Out),SChed_RR(Round Robin)
 RT를 위한 스케쥴링 Policy 

- RR -> 프로세스간 time-slicing (선점 시간할당)
- FIFO -> 우선순위제

리눅스 : nice or renice 또는 chrt로 우선순위 결정
Nice, Renice 는 +19~-20으로 낮을 수록 우선순위가 높음
일반 Process -> nice ||| RT process -> chrt

사용 명령어
chrt -f -p [우선순위 값] [프로세스번호]
| -f : FIFO 사용
| -o : Other 사용
| -r : RR 사용
ps(우선순위 알아보기)

# 2023.3.2 (by PMG)
- 모터 돌리기 성공 -> (CTRL 4번을 GND에 연결, 8번을 가변저항기 가운데에 연결, CTRL 9번 = 5V, CTRL 1번 GND 이렇게 연결한뒤, MDAS에 Send PID Write에 Input_Type을 0으로 두고 
24V에서 진행) : 한 사이클만 돌아가는데 이게 파워 서플라이의 출력이 부족해서 제대로 된 성능이 나오지 않는것 같음)
- 파워 서플라이가 아니라 파워 뱅크를 이용해서 모터를 돌려야 할듯(홍기형 의견) : 220V 선 필요..

# 2023.3.3 (by PMG)
- 모터 속도 조절 하게 만듬 + 모터드라이버 CTRL 핀들 13핀으로 묶음(속도 조절은 가변저항기를 이용해서 속도 조절) + SMPMS을 이용해서 모터 드라이브 작동성공
-- 2(DIR),4(START/STOP) Pin을 GND에 연결해야암 + 가변저항기의 가운데 선을 8(Speed In) 핀과 연결
-- 가변 저항기에 따라 속도가 조절되지만, 발열과 통신 문제 해결해야함.

# 2023.3.6(by PMG)(with KJH)
- 모터 토크 제어 성공 - 자세한건 HOW_TO_CONTROL... txt 파일 참조
- 모터 위치 제어도 성공 -> 자세한건 같이 올린 HOW_TO_CONTROL... txt
- 문제는 엔코더를 이용한 속도제어가 문제라고 생각됨 -> 엔코더를 사용하지 않고 홀센서 만으로 제어하는 ENC_OFF 명령어를 '쓰지 않는 경우' 모터가 덜덜 거리다가 에러를 내고 멈춤
- 이번주부터 STM32를 이용해서 모터 드라이브와의 통신(MDAS를 쓰지 않고)을 진행할 예정
- 모터 테스트 영상 주소 https://drive.google.com/file/d/1O3Y8ixFg5ewMUY9hgxx-sdSBJ0BZhaq9/view?usp=share_link

# 2023.3.7(by KJH)(with PMG)
- stm32와 모터드라이버간 rs485 통신 성공, MDAS를 쓰지 않아도 stm32를 통해 모터드라이버 기본설정 및 전류제어 전류값 명령 송신 가능
- stm32에 들어가는 프로그램 업로드 완료 확인 바람
- stm32와 컴퓨터는 USART2를 통해 시리얼 통신으로 연결되어 있으며 stm32와 모터드라이버는 USART1을 통해 RS485포트로 연결되어 있어야 작동이 됨
- 컴퓨터 시리얼 통신 프로그램으로 stm32에 숫자를 입력해주면 숫자에 맞는 명령들이 수행되게 함
- 추후에는 FREERTOS를 활용해서 제어기 설계를 해 볼 예정

# 2023.3.13(by KJH)
- MPU6050 센서값을 STM32로 받아 칼만필터를 사용, 값을 필터링 하는데 성공함
- 기존 상보필터에서 칼만 필터로 개조함
- 칼만필터 센서값을 출력하는 프로그램 업로드 완료 확인바람
- MPU6050에 3.3V의 전원 인가후 I2C통신을 위한 핀을 연결해주면 STM32 프로그램이 자동으로 I2C 통신을 위한 초기 설정 및 값을 받아옴
- 출력값은 USART 통신을 통해 확인가능 

같은 날 (by PMG)
- MPU6050 센서값을 Raspberry pi로 받아 출력,이후 칼만필터를 이용해서 필터링 예정
- RTOS CYCLE Test 결과는 많이 돌릴수록 MAX 레이턴시는 길어지나 평균은 25us 미만(Thread use1 -> MAX: 240us, Thread use 4-> MAX:320us)
- 블로그 글에서는 MAX도 100이하로 낮아진다고 했는데 이후 재설정 해볼 예정
- I2C에서 Slave를 여러개 달수 있다고 하는데 이후 공부를 좀더 해봐야 겠음(MPU6050을 동시에 두개 돌려보기)


# 2023.3.15(by PMG)
- xenomai라는 RT 리눅스 커널을 알게 되어서 이후 공부해볼 예정
- 일단은 교수님께서 리눅스 커널은 그대로 두고 제어 주기를 500us 정도로 잡고 해보라고 하셨음
- 칼만 필터는 커널 설치가 제대로 된다면 진행하고 안되면 커널이 터져서 고치고 있다라고 간주하시면 됩니다....(MPU6050 두개다 값이 받아지긴함)

#################################################
#################  SENSOR, IC ###################
#################################################

IC --> LM7805, 5v Regulator
Sensor
--> MPU6050 or MPU9250 




final_step. 계단 오르기 ...
( 2023. 3. 06에 작성한 글입니다. 향후 계획은 단계마다 바뀔 수 있습니다.)
