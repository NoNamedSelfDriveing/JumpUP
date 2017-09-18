# Play Asphalt with EEG

### 주제 : 뇌파 분석을 통한 'Asphalt' 게임 플레이
![Asphalt](Asphalt.jpg)
-----
### 개발 동기
뇌파를 이용한 프로젝트를 이전부터 계속 기획하고 있었습니다. 이번 JUMP UP 캠프를 기회로 삼아, 뇌파 데이터를 직접 수집하고 프로세싱하는 작업을 진행해 볼 예정입니다.
사용자들의 흥미를 함양하고 부스 형태 전시에도 알맞은 주제일 것 같아, 개발을 진행하기로 하였습니다.

### 프로젝트 요약
뇌파 수집 헤드셋을 이용하여 사용자의 뇌파 정보를, 자이로 센서를 이용하여 머리의 기울기 정보를 동시에 실시간으로 읽어와서 프로세싱합니다. 뇌파 데이터는 니트로와 브레이크를 제어하는 데에 사용되고, 자이로 센서의 데이터는 자동차의 회전 방향을 제어하는 데에 사용됩니다. 이를 통해, 따로 컨트롤러가 필요 없이, 헤드셋을 착용하고 생각만으로 게임을 플레이할 수 있게 됩니다.

### 프로젝트의 기반 기술
__뇌파 신호 획득과 분석__ : MindWave 헤드셋을 활용한 뇌파 신호 획득을 통해 게임 진행에 필요한 데이터를 수집합니다.

__자이로 센서 데이터 획득과 분석__ : 자이로 센서의 데이터 획득과 분석을 통해, 게임 진행에 필요한 데이터를 수집합니다.

__AVR 제어__ : 뇌파 데이터와 자이로 센서 데이터를 동시에 수집해서 게임이 플레이되고 있는 컴퓨터로 전송하는, 중계기의 역할을 구현합니다.

### 프로젝트 상세 추진 계획
#### 1. 뇌파 데이터 프로세싱
1. MindWave 헤드셋을 사용하여 뇌파 데이터를 읽고 직접 확인해 봅니다.
2. 뇌파 데이터를 주파수 대역에 따라 분리해봅니다.
3. 실제 게임을 플레이하면서 특정 행동을 할 때 뇌파의 변화를 체크합니다.

#### 2. 자이로 센서 데이터 프로세싱
1. 자이로 센서를 사용하여 데이터를 읽고 직접 확인해 봅니다.
2. 헤드셋에 자이로 센서를 부착합니다.
3. 아두이노 나노를 이용하여 자이로 센서 데이터를 AVR로 전송합니다.
4. 자동차의 회전 신호로 판단할 센서 값의 Threshold를 정합니다.

#### 3. 블루투스 통신을 이용한 데이터 전송 구현
1. AVR에서 MindWave 헤드셋과 자이로 센서를 부착한 Arduino NANO와 연결을 구현합니다.
2. 두 데이터를 받는 동시에 UART 통신을 사용해 컴퓨터로 데이터를 전송합니다.
3. 받은 데이터를 이전에 만들어놓은 데이터 기준에 따라 키보드 키 데이터로 변환하여 전송합니다.

### 미래 발전 방향
#### 1. 딥 러닝 활용 뇌파 분류력 향상
저희 동아리에서 학습 중인 딥 러닝을 활용하여 뇌파의 분류력을 향상시키는 것이 첫 번째 미래 목표입니다.
현재 뇌파가 특정 동작을 발생시켜야 하는 뇌파인지 보다 정확하게 판단하기 위해서, 딥 러닝 기술을 활용해 뇌파 분류력을 향상시키는 방법을 사용할 수 있을 것입니다. 이를 향후 프로젝트로 다시 계획할 것입니다.


#### 2. 뇌파 분류 라이브러리 제작
뇌파 분류 라이브러리 제작을 통해서 저희 프로젝트에 맞는 맞춤형 뇌파 분류기를 작성할 수 있을 것입니다. 이를 통해 더욱 정확한 게임 플레이 데이터 수집을 가능케 할 것입니다.

### 프로젝트 추진에 필요한 물품
1. NeuroSky 사 MindWave 헤드셋 2대 : 대당 131,000원 [[Link](http://item.gmarket.co.kr/Item?goodscode=999426085&pos_shop_cd=SH&pos_class_cd=111111111&pos_class_kind=T&keyword_order=MindWave&keyword_seqno=12902348156&search_keyword=MindWave)]
2. AT128A-70B V2.0 : 16,000원 [[Link](http://www.devicemart.co.kr/35264)]
3. Arduino NANO : 30,000원[[Link](http://www.devicemart.co.kr/34411)]
4. UART 확장 모듈 : 24,090원[[Link](http://cr2.shopping.naver.com/adcrNoti.nhn?x=MOfJmOCozcQBRjfKX8Uxi%2F%2F%2F%2Fw%3D%3DsbAttJlTWDBL5S4TY1TxjOQDkTSLbQR1oOgSN5vG%2F3ZP2XSfLr2YqL8oPiAD7ZiycS7Mr8aVazJ1n2qmUBif7KJSZS02dbfVNhbaOrrVtCcAjGIBer7qKMxCpvbnOXBXhxu18RpcDMrLywIMHyLTy0mtmotr%2BSdAnGvQcGEKEMlWrAc%2F%2BlUZ38CWJJAfwMoKAz%2F8rwN6NVKgTNLIZxiDF1UN6Ti%2BwW9mNuVNxwdNNuPoNlgVkPmB3Fk5NKtM%2BH9nOrp4SorNTj22ze7e6OQHQdcpn545QSgAPff3GJwjAgBIhxfFTUuEhjck9K1e9hxUxsE%2FlcJE2bOcft9T84fqPnTn4LsZtYWyg7oKmFjNw7hKhX3ledhJ91y2CHYVLvmutWNcQS%2F9V6J7yQ7Aaf4OOQltoylU6V%2FtAeSdIOegJ6fCv1Qo7fM3J%2Fe%2FVhnj5JjQePvR5S3MHMC%2B5X9IQfTqkGhybbqYg4%2Bpwl1mObahcBgsodoL8d3Y6HOcKfjwjYcmAJ90HeaWvgVmeWBVrSIWUryZPraFLMJLvszaQF1Yp8b7UP0wTW5Ca2bAuqaaJ6SMpLimixFVpHyT891D0zlKD3xQPshV%2BzPtgm3O%2FNnZT8m%2BoLNlnW1xLA1R27qemymWucYCN3UTgzVocZ%2BIVWkYfyW1mD9MG4OXNAG7ECXS7urRoOwKpoihWc%2BGRsEIc6DTH3TzrXeLgOpjI3aey5PCkmAEnpdLR7TbNNPTUR4iSEjDmELD3rZWfKu18oNrMb6tp&nv_mid=9461167328&cat_id=50001579)]
5. MPU6050 : 32,000원[[Link](http://www.devicemart.co.kr/38329)]
6. USB 2.0 mini-B 케이블 : 1,500원[[Link](http://www.devicemart.co.kr/1324029)]
