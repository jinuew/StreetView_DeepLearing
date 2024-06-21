# StreetView_DeepLearing

프로젝트 기간(2024.3월~2024.5월)
[https://jinuew.github.io/webinfo/](https://jinuew.github.io/webinfo/)



연구 개요:<br>
거리뷰 이미지를 활용한 식생 Image Segmentation을 수행하고자 함.<br>
이러한 세그멘테이션은 HumanFOV(사람의 시야각)에서 보이는 식생의 비율을 구할 수 있고, 이러한 지수를 식생 지수인 위성영상의 NDVI 지수와 비교하고자 함.<br>
연구대상지역은 서울시 대학교로 선정함.<br>

연구 일지<br>

2월 16일 기준<br>
Tensorflow, Pytorch 라이브러리를 통해 이미지 딥러닝을 하고자 함.<br>

3월 1일 기준<br>
대상 지역은 점진적으로 광진구로 선정 / 광진구 빅데이터 공모전 출품 예정 ~5/3<br>
YOLO(You Only Look Once)를 통한 객체 탐지 알고리즘 훈련.<br>
Training, Test 및 도로의 차량, 트럭 이외에도 사람, 책상, 노트북, 컵 등을 구별함<br>

3월 6일
구글 스트리트뷰 이미지 다운 코드 활용<br>

3월 13일
Image segmentation 기초 수행 | 해상도에 따라 정확도 차이 발생 + 구글 스트리트뷰 해상도 낮음 문제<br>

앞으로의 방향: 대용량 이미지 저장 및 활용 방안<br>
-> 구글: 해상도 낮음 문제, 캠퍼스 내 스트리트뷰 부재<br>
-> 카카오: 다운은 가능하나 공식 지원 X 및 재가공 불가 방침, 캠퍼스내 로드뷰가 2012년 정도로 부적합<br>
-> 네이버: API를 활용한 대용량 이미지 지원 X 그러나 캠퍼스내 로드뷰가 가장 최신.<br>
--> 캠퍼스 도로를 기준으로 100미터 포인트를 생성함. 포인트의 인접 지역을 직접 캡처를 수행항.<br>
--> 수작업이지만 네이버의 거리뷰 퀄리티가 가장 높다는 점과 정면시야각 자동 보정을 통해 도로의 정면부를 정확하게 캡쳐할 수 있어 일관성있는 HumanFOV를 고려할 수 있음.<br>

3월 18일<br>
스트리트뷰 루프 반복문을 활용한 코드 생성  | 각도 미반영 -> 수작업으로 결정함.<br>

3월 20일<br>
Image segmentation 산림 비율만 산출 | 해상도나 사진 비율이 이상해도 산림 비율은 잘 탐지 함. 오류가 거의 발생하지 않음<br>

3월 24일<br>
서울시 대학교 중 연구하고자 하는 대학교를 선정함. OSM에서 제공하는 대학교 공간 데이터(도로망, 캠퍼스 면적) 등을 고려하여 10개교를 선정하였음.<br>
:건국대학교, 경희대학교, 고려대학교, 삼육대학교, 서울과학기술대학교, 서울대학교, 서울시립대학교, 연세대학교, 이화여자대학교, 한양대학교<br>

3월 30일<br>
![image](https://github.com/jinuew/StreetView_DeepLearing/assets/141210846/fa5631cd-1f84-49ff-8420-380a2fbc63fe)
반복문을 통해 대용량 세그멘테이션을 수행함.<br>
기초 코드는 캐글의 모델을 활용함.<br>

4월 1주차~2주차<br>
각 대학의 대한 그래프, 종합 그래프, 순위 등을 지정할 수 있었음.<br>


4월 3주차<br>
웹 사이트와 결과를 바탕으로한 그래프와 지도를 제작함.<br>
(jinuew.github.io/webinfo)에서 확인이 가능함. 동적 그래프와 GeoJSON등의 파일을 통해 동적 지도를 만들어 웹인포그래픽 활용을 높임.<br>

5월 2주차<br>
연구 내용을 바탕으로 포스터, 발표자료, 연구 논문 등 작성
