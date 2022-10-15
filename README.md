# scv-audit-check-list

|CATEGORY|Check Item                                             |DESCRIPTION                                                                     |
|--------|-------------------------------------------------------|--------------------------------------------------------------------------------|
|Basic Code Bugs|Reuse of ID to be used once                            |1번만 사용되어야 하는 값의 재사용 e.g. 팬케익 로터리                                                |
|Basic Code Bugs|Reference to unupdated variable                        |업데이트되지 않은 변수 참조. e.g. 잔고, 토큰 개수 등                                               |
|Basic Code Bugs|Unchecked CALL Return Values                           |call의 반환 값을 확인하지 않은 경우                                                          |
|Basic Code Bugs|Short Address/ Parameter Attack                        |Short Address 공격, 파라메터, Calldata 검증 부족                                          |
|Basic Code Bugs|Delegatecall                                           |DelegateCall의 잘못된 사용                                                            |
|Basic Code Bugs|Uninitialized Storage Pointers                         |Storage Pointer의 초기화가 이루어 지지 않은 경우                                              |
|Basic Code Bugs|Floating Points and Precision                          |부동 소수점 사용 및 정밀도 문제                                                              |
|Basic Code Bugs|Tx.Origin Authentication                               |Tx.Origin으로 인증하는 경우                                                             |
|Basic Code Bugs|Race Conditions / Front Running                        |Race Condition / Front Running                                                  |
|Basic Code Bugs|Entropy Illusion (Lack of Randomness)                  |랜덤값의 낮은 Entropy                                                                 |
|Basic Code Bugs|Gasless send                                           |가스가 필요 없는 send                                                                  |
|Basic Code Bugs|use Untrusted Libraries                                |신뢰할 수 없는 Library 사용                                                             |
|Basic Code Bugs|Unauthorized Self-Destruct                             |인증 되지 않은 Self-Destruct 호출                                                         |
|Basic Code Bugs|Money-Giving bug                                       |임의의 돈을 인출하거나, 전송할 수 있는 버그                                                       |
|Basic Code Bugs|send Instead Of Transfer                               |Transfer 대신 send를 사용한 경우                                                        |
|Basic Code Bugs|Revert DoS                                             |Revert로 인한 DoS                                                                  |
|Basic Code Bugs|Re-entrancy                                            |재진입 공격                                                                          |
|Basic Code Bugs|Deprecated Uses                                        |사용되지 않는 변수, 함수                                                                  |
|Basic Code Bugs|Redundant Fallback Function                            |불필요한 Fallback 함수                                                                |
|Basic Code Bugs|Blackhole                                              |contract 내 자금 영구 lock                                                  |
|Basic Code Bugs|Ownership Takeover                                     |contract나 함수의 Owner가 잘못 설정되는 경우                                                 |
|Basic Code Bugs|Transcation Ordering Dependence                        |Transcation 순서에 의존하는 로직                                                         |
|Basic Code Bugs|Unchecked External Call                                |검증되지 않은 External call                                                           |
|Basic Code Bugs|Costly Loop                                            |Loop의 가스 값이 과도한 경우                                                              |
|Basic Code Bugs|Overflows & Underflows                                 |오버플로우 & 언더플로우 (체크 안해서 revert 발생 하는 경우)                                        |
|Basic Code Bugs|use predictable Random Variables                       |예측 가능한 랜덤 변수 사용                                                                 |
|Basic Code Bugs|Constructor Mismatch                                   |Constructor가 잘못 된 경우                                                            |
|Semantic Consistency Checks|Semantic consistency Checks                            |코드 일관성                                                                          |
|Advanced DeFi Scrutiny|Possible Price Manipulation Attack                     |가격 조작이 가능한 경우                                                                   |
|Advanced DeFi Scrutiny|Emergency Mechanism                                    |비상 메커니즘 동작 방식                                                                   |
|Advanced DeFi Scrutiny|Authentication Management                              |인증을 올바르게 수행하는지                                                                  |
|Advanced DeFi Scrutiny|Operation Trails & Event Generation                    |이벤트 생성을 올바르게 하는지                                                                               |
|Advanced DeFi Scrutiny|Functionality Checks                                   |정확한 동작을 수행하는지                                                                   |
|Advanced DeFi Scrutiny|Oracle Security                                        |Oracle에 보안 문제가 없는지                                                              |
|Advanced DeFi Scrutiny|Frontend-Contract Integration                          |frontend와 contract 사이의 통합이 이루어 지는지                                              |
|Advanced DeFi Scrutiny|Access Control & Authorization                         |접근 제어 및 owner 설정이 올바른지                                                          |
|Advanced DeFi Scrutiny|Deployment Consistency                                 |배포 일관성                                                                          |
|Advanced DeFi Scrutiny|Digtial Asset Escrow                                   |디지털 자산 중개 거래에 보안 문제가 없는지                                                        |
|Advanced DeFi Scrutiny|Business Logic Review                                  |비즈니스 로직 버그 체크                                                                               |
|Token   |Bound check                                            |amount = 0일 때 처리되는지                                                             |
|Token   |parameter check                                        |Approve, Transfer에 msg.sender와 from을 구분하여 사용했는지                                 |
|Token   |Incorrect asset’s value                                |잘못된 asset value 계산 (e.g. iBUSD vs BUSD)                                         |
|Token   |Compation of Deflationary Token                        |Deflationary Tokens의 확장성을 고려했는지                                                 |
|Token   |Functionality check                                    |정확한 동작을 수행하는지 (Burn을 하지 않음, Transfer 실패 등 )                                    |
|Token   |Mint security                                          |minting에 취약점이 있는지                                                               |
|Token   |ERC 20 Idiosyncrasies Handling                         |ERC-20의 특이사항 handling                                                          |
|NFT Security|sequential ID                                          |NFT의 metadata가 이미 다 공개되어있는 경우 e.g.) ID가 순차적이라면 예측이 가능함.                         |
|NFT Security|Duplicated Item                                        |같은 ID의 NTF가 생성되는 경우                                                             |
|Signature & hash|Unchecked verification of sign                         |서명의 유효성을 검증하지 않은 경우                                                             |
|Signature & hash|Sign without private key                               |서명에 개인키가 포함되어 있지 않은 경우                                                          |
|Signature & hash|can make another vaild sign with vaild Sign            |유효한 서명으로 다른 유효한 서명을 생성 하는 경우                                                    |
|Signature & hash|Sign without nonce                                     |서명에 nonce가 포함되어있지 않은 경우                                                         |
|Signature & hash|Use Same K                                             |서명에 같은 K 가 사용되는 경우                                                              |
|Signature & hash|Hash Collisions With Multiple Variable Length Arguments|서명에 가변 길이 변수가 들어가 충돌이 발생 할 수 있는 경우                                              |
|Signature & hash|Signatures Replay                                      |Replay attack이 가능한지                                                             |
