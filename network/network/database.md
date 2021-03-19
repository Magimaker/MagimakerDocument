---
description: DB(MYSQL)를 사용할 때 필요한 기능들을 구현
---

# database

## 설명

데이터베이스를 사용하는데 필요한 기능들을 구현한 파일입니다.  
다음과 같은 기능들을 제공합니다.

1. DB 연결 및 해제  
2. 쿼리를 실행하여 결과에 담음, 결과에 대한 row 조회  
3. 정보 조회 \(유저, 방\)  
4. 추가 및 삭제 \(유저, 방 , 방 내부 인원 \)  
5. 중복 체크 

##  DB Connect Function

| 함수명 | 설명 |
| :--- | :--- |
| ConnectDB | DB를 서버와 연결 |
| CloseDB | 서버와 연결된 DB를 해제 |

## QueryRun & FetchRow Function

| 함수명 | 설명 |
| :--- | :--- |
| RunQuery | 인자로 받아온 쿼리를 실행하여 결과에 담음 |
| FetchRow | 받아온 결과에 대한 row를 하나씩 차례대로 받아옴 |

## Information Inquiry Function

| 함수명 | 설명 |
| :--- | :--- |
| InquiryCount | 인자로 받아온 테이블에 대한 count를 반환 |
| InfoID | 유저의 ID, PWD를 유저 테이블 값과 비교. 로그인 과정에 사용 |
| BringUserinfo | 유저 테이블을 조회하여 유저의 정보를 담음 |
| BringRoomList | 방 목록 테이블을 조회하여 방 목록 정보를 담음 |
| BroadcastInRoom | 지정된 방 내부 유저에 대한 정보를 담음 |

## Insert & Delete Function

| 함수명 | 설명 |
| :--- | :--- |
| JoinMembership | 회원가입한 유저의 정보를 유저 테이블에 추가  |
| CreateRoom | 방 생성시 방 목록 테이블에 추가 |
| EnterRoom | 방 입장시 방 내부 유저의 정보를 가져오고 입장한 유저의 정보를 추가 |
| ExitRoom | 호스트를 제외한 유저가 퇴장시 방의 정보를 갱신 |
| DeleteRoom | 방 목록 테이블에서 지정된 방을 목록에서 제거 |

## Check Function

| 함수명 | 설명 |
| :--- | :--- |
| CheckRoomid | 방 목록 테이블에서 방 식별자\(rid\)가 중간에 빈 것이 있는지 확인 |
| SQLDuplicateCheckRid | 동일한 방 식별자가 있는지 확인 |

