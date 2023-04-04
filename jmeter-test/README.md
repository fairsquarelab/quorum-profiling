기타 내용은 기존 README.md 참고  

## 수행 방법
properties 파일 등 맞춰주고 다음과 같이 수행
```
jmeter -n -t ./4node/deploy-contract-public.jmx -q sample-network.properties
```

## 수정한 내용
 | 수정한 파일 | 내용 | 비고 |
 | --------- | -------- | --------- |
 | 공통 | Disabling `influxDB` (하단 내용 참고) | |
 | `1node/deploy-contract-websocket` | websocket 방식 | |
 | `1node/deploy-erc20-contract-public` | ERC20 컨트랙트 배포 | |
 | `1node/deploy-erc1400-contract-public` | ERC1400 컨트랙트 배포 | |
 | `update-contract-public-nonce` | nonce값 명시적으로 세팅 | 실행시 `Nonce Generator` start 값 알맞게 맞춰 줘야 함 |
## Disabling `influxDB` 
 In order to run tests without metrics being pushed to `influxDB`, disable the listener by replacing the below line in the test plan jmx files
 
``<BackendListener guiclass="BackendListenerGui" testclass="BackendListener" testname="Backend Listener" enabled="false">``
