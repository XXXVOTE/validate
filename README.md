# UOSVOTE 검증하기

사용자가 투표한 결과 벡터의 암호문은 공개된 네트워크인 IPFS에 등록됩니다.
https://gateway.pinata.cloud/ipfs/HASHVALUE 를 통해 웹에서 확인할 수 있는 해쉬값
에 대한 암호문을 다운로드 받을 수 있습니다. cipher 폴더 내에 모두 다운로드 받습
니다.

암호문을 만들 때 사용되는 공개키는 아마존 S3에 저장되어 있습니다.
https://uosvotepk.s3.ap-northeast-2.amazonaws.com/election/ELECTIONID/ELECTIONID-ENCRYPTION.txt
의 형식으로 ELECTIONID로 다운로드할 수 있습니다.

UosVote는 Microsoft의 node-seal을 이용하고 있습니다. npm install 후 add 함수를
실행하면 cipher 폴더 내의 모든 암호문을 읽어 RESULT를 만듭니다.

투표 결과창에 있는 최종 RESULT 파일을 다운로드 받아 두 파일에 대한 해쉬값을 비교
하면 같은 결과를 얻을 수 있습니다. 다른 파일을 추가하거나 모두 포함하여 덧셈 연
산을 하지 않으면 같은 해쉬값을 구할 수 없습니다.
