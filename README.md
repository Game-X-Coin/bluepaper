# GameXCoin Blue Paper v1.2

2018년 10월 O일

GameXCoin은 게임과 잘 결합*well-integrated* 할 수 있도록 설계된 새로운 블록체인 플랫폼이다. 다양한 탈중앙화 애플리케이션 구동을 위해 설계된 범용 목적의 블록체인과 달리 GameXCoin 블록체인은 게임과 결합하였을 때 최상의 성능과 결과물을 낼 수 있도록 작성되었으며 게임 성능에 영향을 미칠 수 있는 기능은 제한될 수 있다. GameXCoin과 결합된 게임을 작성하는 제작자는 블록체인에 대한 이해 없이도 제공되는 SDK를 활용하여 게임에 블록체인 요소를 도입할 수 있다. 블록 생성자와 GXC 보유자는 네트워크 유지에 기여한 대가로 보상을 받으며 게임 유저는 플레이를 통한 토큰 획득, 게임 투표 참여 등을 통해 네트워크를 성장 시키고 블록체인과 게임을 결합하여 갖게 되는 장점의 직접적인 수혜자가 된다. GameXCoin은 메인넷 런칭 단계에서 완성 및 개발이 종료되는 플랫폼이 아니라 블록체인 기술 성장에 따라 변화해가는 지속 발전형 플랫폼이다.

Copyright © 2018 블록체인벤처스

> **Disclaimer:** 본 GameXCoin 청서*blue paper*는 GameXCoin의 로드맵, 기능에 관한 정보 제공을 위해 작성하였으며 참고 목적으로만 사용해야 합니다. 청서는 투자를 권유하고 있지 않으며 이러한 목적과 전혀 무관함을 분명히 밝힙니다. 청서는 작성 당시의 상태를 기준(AS-IS)으로 작성하였으며, 청서에 작성된 내용이 백서*white paper*나 홈페이지에서 제공하는 내용과 다른 경우 청서 내용이 우선함을 원칙으로 합니다. 블록체인벤처스는 독자가 이 청서를 읽는 시점 및 그 장래에 대해 로드맵에 계획된 GameXCoin 프로젝트의 결론, 일정, 성과를 포함하여 청서상에 기재된 어떠한 내용에 관하여도 그 내용이 정확하거나 적절함을 보증하지 않습니다. 청서는 블록체인벤처스의 정책 또는 의사결정에 따라 내용이 변경될 수 있습니다.

- [GameXCoin Blue Paper v1.2](#gamexcoin-blue-paper-v12)
- [배경](#%EB%B0%B0%EA%B2%BD)
- [2. GameXCoin Ecosystem](#2-gamexcoin-ecosystem)
  - [2.1. Blockchain Game](#21-blockchain-game)
    - [2.1.1. Blockchain as Marketing - Escrow Pool](#211-blockchain-as-marketing---escrow-pool)
    - [2.1.2. Blockchain as Money - Game Blockchain](#212-blockchain-as-money---game-blockchain)
      - [2.1.2.1. Gaming as Mining](#2121-gaming-as-mining)
    - [2.1.3. Blockchain as Governance - Blockchain Game](#213-blockchain-as-governance---blockchain-game)
    - [2.1.4. Summary](#214-summary)
  - [2.2. Game Developer](#22-game-developer)
    - [2.2.1. Register Game](#221-register-game)
    - [2.2.2. Issue Token](#222-issue-token)
    - [2.2.3. Register Event](#223-register-event)
    - [2.2.4. Token Management](#224-token-management)
  - [2.3. Gamer](#23-gamer)
    - [2.3.1. Play Game, Get Tokens](#231-play-game-get-tokens)
    - [2.3.2. Token Usage](#232-token-usage)
      - [2.3.2.1. Escrow Pool](#2321-escrow-pool)
      - [2.3.2.2. In App Usage](#2322-in-app-usage)
      - [2.3.2.3. Claim GXC](#2323-claim-gxc)
      - [2.3.2.4. Sell Token](#2324-sell-token)
    - [2.3.3. GXC Usage](#233-gxc-usage)
      - [2.3.3.1. Vote for Block Producers](#2331-vote-for-block-producers)
      - [2.3.3.2. Vote for Games](#2332-vote-for-games)
      - [2.3.3.3. Buy Token](#2333-buy-token)
    - [2.4. Game Use Case](#24-game-use-case)
    - [2.4.1. Single Play Game](#241-single-play-game)
    - [2.4.2. Multi Play Game](#242-multi-play-game)
    - [2.4.3. Crypto Game](#243-crypto-game)
  - [2.5. Token Economy](#25-token-economy)
- [3. Blockchain](#3-blockchain)
  - [3.1. DPoS](#31-dpos)
  - [3.2. Native Action and System Contract](#32-native-action-and-system-contract)
    - [3.2.1. Make the common case cheap, fast.](#321-make-the-common-case-cheap-fast)
    - [3.2.2. Limitations of EOSIO’s Contract](#322-limitations-of-eosios-contract)
    - [3.2.3. Characteristics of GXC Native Action](#323-characteristics-of-gxc-native-action)
    - [3.2.4. Native Action Rule](#324-native-action-rule)
    - [3.2.5. Type of Native Action](#325-type-of-native-action)
      - [3.2.5.1. Game Contract](#3251-game-contract)
      - [3.2.5.2. Token Model](#3252-token-model)
      - [3.2.5.3. 탈중앙화 거래소(DEX)](#3253-%ED%83%88%EC%A4%91%EC%95%99%ED%99%94-%EA%B1%B0%EB%9E%98%EC%86%8Cdex)
    - [3.2.6. Fees](#326-fees)
    - [3.2.7. 예외 상황에 대한 컨트롤](#327-%EC%98%88%EC%99%B8-%EC%83%81%ED%99%A9%EC%97%90-%EB%8C%80%ED%95%9C-%EC%BB%A8%ED%8A%B8%EB%A1%A4)
  - [3.3. Accounts](#33-accounts)
    - [3.3.1. Permission](#331-permission)
    - [3.3.2. Anonymous Account](#332-anonymous-account)
  - [3.4. Make the rare case correct.](#34-make-the-rare-case-correct)
  - [3.5. Sidechain](#35-sidechain)
- [4. Governance](#4-governance)
  - [4.1. Block Producer](#41-block-producer)
    - [4.1.1. 구성](#411-%EA%B5%AC%EC%84%B1)
    - [4.1.2. 역할](#412-%EC%97%AD%ED%95%A0)
      - [4.1.2.1. 블록생성](#4121-%EB%B8%94%EB%A1%9D%EC%83%9D%EC%84%B1)
      - [4.1.2.2. Resource 제공](#4122-resource-%EC%A0%9C%EA%B3%B5)
    - [4.1.3. 권한](#413-%EA%B6%8C%ED%95%9C)
      - [4.1.3.1. Parameter](#4131-parameter)
      - [4.1.3.2. 계정정지](#4132-%EA%B3%84%EC%A0%95%EC%A0%95%EC%A7%80)
      - [4.1.3.3. Token Pause for abusing games](#4133-token-pause-for-abusing-games)
  - [4.2. GXC Holders](#42-gxc-holders)
    - [4.2.1. Voting](#421-voting)
      - [4.2.1.1. Voting for Block Producers](#4211-voting-for-block-producers)
      - [4.2.1.2. Voting for Games](#4212-voting-for-games)
  - [4.3. Work Proposal](#43-work-proposal)
  - [4.4. Inflation](#44-inflation)
    - [4.4.1. Inflation의 분배](#441-inflation%EC%9D%98-%EB%B6%84%EB%B0%B0)
- [5. Products](#5-products)
  - [5.1. GXC.World](#51-gxcworld)
    - [5.1.1. Wallet](#511-wallet)
    - [5.1.2. Gaming Portal](#512-gaming-portal)
    - [5.1.3. DEX](#513-dex)
  - [5.2. Dev.World](#52-devworld)
    - [5.2.1. 관리공간](#521-%EA%B4%80%EB%A6%AC%EA%B3%B5%EA%B0%84)
    - [5.2.2. 개발 도구](#522-%EA%B0%9C%EB%B0%9C-%EB%8F%84%EA%B5%AC)
  - [5.3. Chain.World](#53-chainworld)
- [6. Summary](#6-summary)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>

# 1. 배경

**Tokenize your game, Monetize your play!**

1961년 최초의 컴퓨터 게임인 <Spacewar!>의 등장 이후 게임 시장은 전례 없이 빠른 속도로 성장해왔다. 군사, 과학 목적의 고속 계산 장치인 컴퓨터를 심심풀이 용도로 활용하기 위해 처음 만들어진 게임이 이제는 게임을 원활하게 작동시킬 수 있도록 하드웨어 개발을 선도하고 있다. 화면상의 점을 상하좌우로 이동시키는 단순한 조작에 불과하던 게임은 이제 자체적인 경제 시스템을 갖추고 디지털 자산인 게임 화폐와 아이템을 거래하며, 이를 현실의 통화*Fiat money*로까지 교환하는 거대한 생태계를 구축했다.

그러나 현재의 게임 시장은 제작사, 유통사, 유저의 한 방향으로만 이어진 일방적 관계로 제한되어 있다. 게임 유저는 다른 생태계에선 찾아보기 힘든 수준의 적극적 참여자지만 가장 수동적인 역할을 맡아 게임을 구매할 것인가, 플레이 할 것인가 등 소극적 의사 표현 밖에 할 수 없다. 블록체인을 활용한 암호 경제는 **암호 화폐인 토큰**과 **참여자들의 합의**로 운영되는 특징을 갖는다. 토큰으로 치환 가능한 디지털 자산과 적극적 참여층을 이미 가진 게임 시장은 블록체인과 결합하여 새로운 생태계를 낳을 가능성이 가장 높은 분야이다.

자유 시장에서 각 참여자가 자신의 이익을 추구하는 가운데 시장 효율이 달성되는 것처럼 블록체인 네트워크에서는 게임 유저, 게임 제작자, 토큰 보유자*token holder*, 블록 생성자*block producer*가 각자 자신의 이익에 따라 행동하는 일이 네트워크를 성장시켜 가치를 증대시킨다. 참여자 간 합의에 따라 네트워크 성장에 기여하는 행위는 보상을 받고 악의적인 행동은 경제적인 불이익을 통해 제한된다.

**GameXCoin**은 게임과 잘 결합된*well-integrated* 블록체인 플랫폼을 제공하고자 한다. 플랫폼 위에 조성된 새로운 게임 생태계에서 각 참여자들은 기존에 없던 새로운 가치(실시간성, 양방향성, 상호연결성, 경제적 이익 분배, 신뢰성 등)를 누리고 공유한다. 본 문서는 GameXCoin의 작동 원리 및 각 구성 요소인 생태계, 블록체인, 거버넌스, 제품에 관해 기술하고 있다.



# 2. GameXCoin Ecosystem

- 예치*stake*는 투표에 참여하기 위해 **GXC 코인**(이하 GXC)을 메인 네트워크에 맡기는 행위를 의미한다. 예치한 GXC는 일정 시간이 지나면 돌려받을 수 있다.
- **게임 토큰**(이하 토큰)은 GameXCoin 네트워크에서 게임 제작자가 자체적으로 발행하는 통화를 의미한다.
- 에스크로 풀*Escrow Pool*은 GXC와 교환 비율이 고정된 토큰을 발행할 때, 기초 자산으로 사용하기 위해 게임사가 입금한 GXC가 보관되는 영역을 의미한다.
- 리저브 풀*Reserve Pool*은 유저의 네트워크 참여에 대한 보상을 위해 인플레이션의 일부가 게임별로 저장되는 영역을 의미한다.

![](https://lh5.googleusercontent.com/BrY7FC5_rReUYxIFSYzNLG3ICIewcs-2x_OSxXfM8jqhLRRRTF3s3ci98KtoZGp8mLzYIKlCYPlue8yFCQdBYNCDlqusmNg1nrM6h21Y1eeSfvg1feY8JnONLjlhhdD2fGs2Fvvh)

GameXCoin Ecosystem은 게임과 블록체인을 결합하여, 게임사는 더 좋은 게임을 만들어 GXCIO와 결합할 유인을, 유저는 게임을 지속적으로 플레이할 유인을, 그리고 GXC 보유자는 GXC를 보유하여 생태계를 계속 만들어나갈 유인을 제공해준다.
게임사는 GXCIO에 게임을 등록하고, 게임에 사용될 토큰을 발행한다. 이 토큰의 발행 및 유통은 GXCIO에 기록된다. 토큰은 게임사가 지정한 이벤트에 따라 유저에게 배분되고, 유저는 획득한 토큰을 GXC로 바꾸거나, 게임 내에서 소비할 수 있다.

게이머는 GXC.World(5.1) 를 통해 본인이 Staking한 GXC를 이용, 게임을 평가할 수 있다. 이 평가는 일정 기간마다 집계되며, 전체 Claim 대비 본인의 Claim 비율에 따라 GXC를 얻게 된다.  

## 2.1. Blockchain Game

우리는 GXCIO와 결합되는 블록체인 게임을 세 분류로 구분한다. 각 분류에서는 블록체인이 쓰이는 용도 및 결합도가 다르다. 2.1.1과 2.1.2는 게임상의 화폐 역할을 Token이 대체하는 모델이며, 2.1.3은 그것을 넘어 게임과 블록체인이 완전히 결합된 모델이다.


### 2.1.1. Blockchain as Marketing  - Escrow Pool

게임사는 GXC를 에스크로 풀(Escorw Pool)에 넣고, 자사 게임에 사용할 토큰을 발행하고, 유저가 이를 얻을 수 있는 이벤트를 등록한다. 유저는 게임을 플레이하여 토큰을 획득하고, 이 토큰을 이용하여 에스크로 풀에 넣어진 GXC와 교환해갈 수 있다. 교환비는 GXC 대비 얼마의 토큰을 발행 했는지에 의해 결정된다. 

예를 들어 GameXQuest라는 데모 게임에서 GXCIO 에스크로풀을 이용하여 토큰을 배포하는 경우를 생각해보자. 해당 토큰의 이름은 gxq이고, 100GXC를 에스크로 풀에 넣어 1,000개의 gxq를 발행한다. gxq는 0.1GXC의 가치를 가지며, 게임을 플레이하여 10gxq를 얻은 유저는 1GXC를 에스크로 풀에서 교환해 갈 수 있다.

이 단계는 게임과 GXCIO와의 느슨한 결합을 만들어, 블록체인 게이머들이 해당 게임에 들어올 수 있는 초기 창구 역할을 해 줄 것이다.

### 2.1.2. Blockchain as Money - Game Blockchain

우리는 2.1.1.에서 좀 더 나아간 토큰 모델을 상상해볼 수 있다. 기존 게임에서의 화폐모델을 대체 가능하면서, 유저가 게임을 플레이하는 것만으로도 네트워크를 더 풍성하게 하는 모델이다. 이는 gaming as mining이 가능하도록 설계가 된 GXCIO의 특성을 통해 이루어게된다. 토큰의 가치는 게임의 인기 및 해당 게임의 게이머의 참여에 의해 형성되게 된다. 게임사가 정해둔 교환비에 의해 토큰의 가치가 정해지는 2.1.1.의 모델보다 더 블록체인과 더 강하게 결합된다.


#### 2.1.2.1. Gaming as Mining

![](https://lh5.googleusercontent.com/KVKWRbrT_Ht926a-q6EqcT4CfhH8YFlVy9gL6FPzVkxpXHY98bc2jdvYqJWJh_8ONsNH2V0ynRbTMthrpg12O9JdS6Q0E_3UZI6rA2-PNGQJmP9WXowZroOepg7bIsEvtDjpo80o)

![](https://lh5.googleusercontent.com/7P4ZpBeu2a5X039_fTxIXFPuJxHacOP1mwUYoN6suPg1ssfsah56bN5FGe6EA1dz7fsd66VGh7dwv6mz_LlVQ4DxSf_NFOGny1UeqkYFEvcmKbSIgW148uA6uJHF4y7owUmCPKtr)

GXCIO에서 GXC는 정해진 비율에 따라(4.3) 지속적으로 발행되는데, 그 중 일부는 게임 및 게이머에게 지급하게 된다. 이는 ‘GXC Staking’, ‘게임 투표', ‘토큰 Claim' 세 단계를 통해 이루어진다. 

투표과정에 참여하고자 하는 유저는 본인의 GXC를 Staking하여, 투표할 권리를 갖는다. 투표권은 Staking한 GXC의 양에 비례한다.
게임 투표는 이 ‘Staking’ 한 GXC를 활용하여 참여하며, 그 과정 및 결과는 GXCIO에 기록된다. 투표는 2주간 진행되게 되며, 그 결과에 따라 추가 발행된 GXC중 일부가(4.3) 게임의 Reserve Pool에 분배된다.

![](https://lh4.googleusercontent.com/VpK5dCIAHrkYZWYEQbAeMtIP5GDdOM9bJLbj-Xec5bKMAyQs-xySwIde2p1z2VESnumsGV7OtNPzY4S7VtlnFmsrqGKaEYuI43JIOyFWVQExKJy6N_gI37sfqmMXFuclbfyU3C0D)

토큰 Claim은 게이머가 Reserve Pool에 저장된 GXC를 토큰을 이용하여 획득하는 단계이다. 유저는 본인이 그 게임을 플레이하여 얻은 토큰을 Reserve Pool에 쌓인 GXC를 얻는데 사용할 수 있다. 권리를 행사하기 위해선 게이머는 해당 게임을 플레이하여 얻은 토큰을 소모해야 되며, 이 때의 교환비는 2주간 Claim된 토큰의 전체양과 2주전에 쌓인 GXC의 양의 비율이다.

이런 장치를 통해, 게이머는 자신이 좋아하는 게임에 자발적으로 투표할 유인을 갖게 되고, 유저에게 즐거움을 준 게임에게 더 큰 효용을 주는 공정한 보상 체계가 만들어진다. 또한 2.1.1에서 제시하는 에스크로 풀을 통한 게임사가 정의한 Token과 GXC와의 교환가치를 넘어선 교환가치를 ‘지속적'으로 가질 수 있게 된다.

### 2.1.3. Blockchain as Governance - Blockchain Game


2.1.2 모델은 게임의 화폐를 “완전 대체가능”하고, 게이머의 플레이가 GXC를 Mining 하는 효과까지 나올 수 있는 그림을 제시한다. 이와 같은 강한 결합 모델은 블록체인의 토큰 이코노미를 게임의 로직과 결합한 Blockchain Game이 될 것이다.

화폐 뿐만 아니라, 게임 내 재화의 대부분이 GXCIO를 통해 저장, 기록되며 재화의 발급 및 이동, 소모에 대한 모든 동작이 블록체인 상에 저장된다. 게임 자체가 블록체인이며, 이를 통한 토큰 이코노미 세계가 게임 상에 펼쳐지게 된다. 해당 모델이 어떤식으로 동작할지는 블록체인이 더 발전하고, 이와 결합된 게임의 형태가 어떤 모습일지에 대한 연구 및 실행이 계속되면서 제시될 것이라 본다.

### 2.1.4. Summary

앞서 제시한 게임의 세 분류는 임의의 분류이고, 정확히 나누어 떨어지는 모델이 아니다. 특정 게임은 두 개의 분류를 모두 활용하는 모습을 보일 수 있고, 세 분류를 넘어선 다른 개념의 게임이 제시될 수도 있다. 뒤에 제시된 모델일수록 블록체인과의 결합도가 높지만, 각각의 모델이 더 발전된 모습을 의미하는 것은 아니며, 상호배타적이지 않다. 

## 2.2. Game Developer

게임 개발자는 게임 세계를 창조하고, 로직을 기획하는 주체이다. 개발자는 GXCIO에 게임을 등록하고, 게임에 사용될 토큰을 발행한다. 이들은 게임이 어떻게 GXCIO와 결합될지를 결정하고, 유저는 그 결합의 형태를 스마트 컨트랙트를 통해 확인가능하다.
 
### 2.2.1. Register Game


IO에 연동을 원하는 개발자는 게임을 GXCIO에 등록하여야 한다. 이 등록은 컨트랙트를 통해 블록체인에 기록되며 게임사는 직접 컨트랙을 콜하거나, Developer Console(5.2)을 통해 등록할 수 있다.

### 2.2.2. Issue  Token

등록된 게임에서 사용될 토큰을 컨트랙트를 통해 발행할 수 있다. 해당 토큰은 미리 정의된 Preset을 이용하거나 이를 조합하여 발행된다. Preset은 게임에 결합될 형태에 따라 다르게 선택할 수 있다. 예시로는 2.1의 각각의 형태를 따르는 Preset이 있을 것이다. 게이머는 토큰이 발행된 게임, 토큰의 형태, 발급 수량등을 투명하게 조회할 수 있다.

### 2.2.3. Register Event

게임사는 토큰 지급 규칙을 Event로 등록해서 관리한다. 이벤트는 스마트 컨트랙트로 규약되는 토큰 획득에 대한 약속을 의미한다. 예를 들면 게임 최초 로그인 10회 수행 시 10 GXQ 획득, 보스 mob을 처음 제거했을 시 100gxq 획득 등을 들 수 있다.

### 2.2.4. Token Management

게임사는 토큰이 얼마나 발행됬고, 얼마나 Claim 되었는지를 실시간으로 확인할 수 있다. 이를 통해 앞으로의 토큰 발행 및 회수에 대한 계획을 통해 게임의 토큰 이코노미를 지속적으로 잘 돌아가게 할 수 있다. 


## 2.3. Gamer

게이머는 GXCIO에 등록된 게임을 플레이하고, Token 및 GXC를 획득하고, 획득한 GXC로 게임 투표, In App Purchase, 게임 구매 등의 행위를 하여 GXCIO를 더욱 풍성하게 하는 주체이다.


### 2.3.1. Play Game, Get Tokens

게이머는 게임을 플레이하는 도중 2.2.3에 의해 등록된 이벤트를 완수하여 토큰을 획득할 수 있다. 획득할 수 있는 토큰의 양은 개발자가 2.2.3에 의해 기설정된 양을 따른다.

### 2.3.2. Token Usage

게이머가 게임 플레이를 통해 얻은 토큰은 다양한 방식으로 사용이 가능하다. 

#### 2.3.2.1. Escrow Pool

게임사는 2.1.1 의 방식으로 토큰을 발행할 수 있으며, 유저는 해당 토큰을 획득하여 에스크로 풀에 담겨있는 GXC와 교환할 수 있다. 

#### 2.3.2.2. In App Usage

게임사는 토큰을 사용할 수 있는 용처를 게임 내에 디자인할 수 있다. (예시: ‘태양의 직검’ 구매, 보스방 출입권 구매, 게임 이용 시간 등) 유저는 토큰을 사용하여 이러한 재화를 구매가능하고, 게임사는 게이머에게 분배된 토큰을 회수할 수 있다.

#### 2.3.2.3. Claim GXC

Inflation으로 발생한 GXC의 일부는 게임의 인기에 따라 각 게임의 Reserve Pool에 등록이 되고, 게이머는 본인이 얻은 토큰을 통해 Reserve Pool에 등록된 코인을 Claim할 수 있다. 이는 게임사가 디자인한 토큰 이코노미를 넘어선 토큰의 사용처이며, GXCIO 네트워크 확장에 가장 큰 요소가 될 것이다.

#### 2.3.2.4. Sell Token

게이머는 GXCIO 탈중앙화 거래소를 이용하여 자신이 획득한 토큰을 즉각적으로 GXC와 교환할 수 있다. 이는 시스템에 내재된 방식이 아닌, P2P 거래를 통해 GXC를 얻을 수 있는 방법이며 2.3.2.1과 2.3.2.3의 행위와 함께 토큰의 실제 GXC와의 교환비를 생성해갈 것이다. 

### 2.3.3. GXC Usage

토큰을 통해 획득한 GXC는 GXCIO의 통화이며, 시스템 내의 다양한 역할을 하는데 있어 필요한 재화이다.

#### 2.3.3.1. Vote for Block Producers

GXCIO는 DPoS 합의 알고리즘을 통해 체인을 생성하며, 이는 필수적으로 Block을 생산할 Block Producer들을 뽑는 절차를 필요로 한다. GXC를 보유한 홀더는 투표를 통해 누가 Block을 생성할 지에 대해 의사표현할 수 있다. 해당 사안은 Governance(4.1) 장에서 추가로 기술한다.

#### 2.3.3.2. Vote for Games

GXCIO는 자체적으로 Gamification(2.1.2)에 해당하는 로직을 가지고 있는데, 이것이 동작하게 하는 가장 큰 요소는 Game에 대한 Voting이다. GXC 홀더 및 게이머는 어떤 게임이 가장 재미 있는 지를 투표할 수 있고, 이 투표 결과에 따라 게임 Reserve Pool에 할당되는 GXC가 결정된다.

#### 2.3.3.3. Buy Token

유저는 게임 내에 유통되는 재화를 사기 위해 GXC를 소비할 수 있다. 이는 5.1. 에서 제공되는 탈중앙화 거래소를 통해 쉽고 빠르게 이루어질 수 있다.
	
### 2.4. Game Use Case

여러 종류의 게임이 GXC와 연동되어 GXC 네트워크에 들어와 유저를 모으고, 어떻게 중간자 문제를 해결할 수 있는 지에 대해 살펴보자. 예로 제시된 게임들은 GXC Testnet Network에서 실제 돌아가는 POC(Proof of Concept)게임이다.

### 2.4.1. Single Play Game

싱글 게임과 GXC와의 연동이 가능하다. Game의 부분유료화 모델을 GXC 토큰으로 대체할 수 있으며, 이를 통해 개발자는 In App Purchase에 부담되는 수수료를 0에 가깝게 줄일 수 있다. 

이런 모델을 적용한 예시로, 데모 게임 Game X Jelly를 들 수 있다(https://play.google.com/store/apps/details?id=com.GXC.gamexjelly).  Game X Jelly는 모바일에서 구동하는 싱글 게임이며, In App Purchase로 구매가능한 재화인 JLY를 GameXCoin 게임 토큰으로 구현하였다. JLY는 게임에서 특정 이벤트를 해결할 시 유저에게 발급이되며, 해당 JLY를 통해 새로운 시나리오를 오픈하거나, 탈중앙화 거래소 거래를 통해 GXC와 교환할 수 있다.

### 2.4.2. Multi Play Game

유저간의 상호 Action이 있는 멀티플레이 게임은 GXCIO와의 연동을 여러 모델을 통해 구현할 수 있다.  에스크로 기능(2.1.1)을 이용한 마케팅용 토큰, 게임 내에서 얻을 수 있는 기본 화폐나 In App Purchase를 대체하는 화폐를 생각해 볼 수 있다.

데모 게임인 GXCQuest와 Game X Rogue는 웹 MMORPG이며, 각 게임은 GameXCoin 네트워크에서 돌아가는 토큰이 게임상에서 사용된다. 이는 In App Purchase를 대체하는 용도(Game X Rogue)나 게임 내 기본 화폐를 대체하는 용도(GXC Quest)로 각각 쓰인다.

### 2.4.3. Crypto Game

게임 내 화폐 이외의 아이템, 케릭터 등의 재화가 GXCIO에 올라간 형태도 구현 가능하다. 이는 인 게임 로직까지 GXCIO의 Smart Contract를 통해 구현한 형태일 수 있다. 이를 통해 게임 내의 아이템 생성 로직, 갓챠 확률 등을 유저에게 투명하게 공개할 수 있으며, 이 자체가 하나의 token economy를 구성할 것이다. 이러한 형태로는 Crypto Kitties나, Zombie Battle Ground, web 땅따먹기 게임류를 생각해 볼 수 있으며 이브 온라인 같은 재화 자체가 현금 가치과 굉장히 큰 대규모의 MMORPG도 크립토 이코노미를 적용하여 GXCIO 에 올릴 수 있을 것이다.

## 2.5. Token Economy

2장에서 제시한 GXC Ecosystem은 4장에서 제시되는 Block Producer와, Inflation과 결합되어 GXCIO의 Token Economy를 형성한다.

Block Producer는 GXCIO가 동작가능케 하고, BP들의 투표를 통해 GXCIO의 주요 의사결정을 진행한다. 이들은 이런 행위에 대한 대가로 GXC를 얻으며, 성실히, 공정히 해당 직무를 수행할 유인을 갖게 된다.

게임 개발자는 GXCIO에 게임을 등록하고, Token을 발행, 지급, 소모하는 룰을 게임에서 제공한다. 이들은 GXCIO의 유저를 자기의 게임에 끌어들일 수 있으며, GXCIO Gamification(2.1.2.1)은 이를 더 잘 일어날 수 있게 해준다. 또한 GXC를 이용하여 In App Purchase, Game Sale 기능을 구현, 0에 가까운 수수료로 수익을 얻게 된다.

게이머는 게임을 플레이하여 토큰을 획득, 획득한 토큰을 다양한 방법을 통해 GXC 교환이 가능하고, 그 반대도 가능하다. 게이머는 본인이 원하는 바에 따라 GXC 및 토큰을 활용할 수 있다. 

GXC Holder는 BP일수도, 게임 개발자일 수도, 게이머일 수도 있다. 복수개의 역할을 하는 Holder는 본인에 의사에 따라 GXC를 Staking하여 BP 투표, 게임 투표를 진행한다.

GXCIO의 네트워크 참여자는 각자의 이익을 위해 역할을 수행하지만, 이 수행 결과는 결과적으로 GXC의 네트워크 가치를 높이고, 더 많은 게임, 게이머가 GXCIO에 들어오는데 기여하게 된다.

# 3. Blockchain

GXCIO는 EOSIO를 체인을 포크하여 블록체인이 구성된다. 이는 GXC는 DPoS를 합의 프로토콜로 사용하며 OS를 지향하며, 계정별 권한을 활용할 수 있고, WASM을 이용한 스마트 컨트랙트 작성의 특성 등을 지님을 의미한다.

GXC 메인넷은 여기서 더 나아가, EOSIO에서 보다 게임에 더 적합한 생태계를 제공하기 위해 여러 요소들이 추가, 변경된다. 이 장은 GXC 메인넷에서  추가, 변경되는 내용을 중심으로 서술한다.


## 3.1. DPoS

GXCIO는 DPoS(Delegated Proof of Stake)를 컨센서스로 하여 운영된다. 이는 EOSIO에서와의 방식과 동일하나, Block Producer(이하 BP)나 예비 BP들의 숫자 등이 다르게 구성될 수 있다.

## 3.2. Native Action and System Contract

Native action 및 시스템 컨트랙트는 시스템 레벨에서 동작하는 기능이다. 가령 EOSIO에서 Account 생성 관련 기능은 Native Action기능으로 분류된다. GXCIO는 게임 및 게임 토큰, 그리고 이 활용에 대한 로직을 Native Action으로 등록하여 이 부분에 대한 특별한 자원관리 및 로직을 적용한다.

### 3.2.1. Make the common case cheap, fast.

이더리움의 스마트 컨트랙트는 ‘Code is a law.’의 개념을 스마트 컨트랙트를 통해 구현하였다. 이는 블록체인과 암호화폐의 차원을 한 단계 올려주었다. 그러나 스마트 컨트랙트는 비싸고, 느리고, 유지보수하기 힘든 한계를 지녔다. 이오스는 이를 보다 빠르게 합의를 할 수 있는 DpoS Consensus 채택과 추후에 추가될 Parallel Processing으로 극복하려 한다. 그러나, EOS도 희소한 자원을 이해관계자들에게 Allocation하는 모델의 한계에 의해 제대로 된 DApp을 만들 환경을 제시하지 못하고 있다.

GXC는 문제를 좀 더 다른 방향으로 접근하려고 한다. David A. Patterson는  “8 great ideas in computer architecture”을 제시하는데, 우리는 이 구절 중 3절, “make the common case fast”의 컨셉을 보다 더 잘 적용시키려고 한다.

이더리움의 스마트 컨트랙트는 굉장히 다양한 컨트랙트의 작성의 가능성을 이야기하고, 실제로 다양한 컨트랙트가 이더리움 네트워크에서 올라오고 실행됬다.

그러나 그 컨트랙트의 대부분은 어떤 형태였는가? 다시 말해 가장 많은 유형의 컨트랙트는 무엇이었는가? 대부분의 컨트랙트는 ERC20의 토큰 컨트랙트와, 이를 이더리움을 이용해 판매하는 세일 컨트랙트였다. 토큰의 생성, 이동, 판매는 지금도 이더리움의 가장 많은 트랜잭션을 차지한다.

GXC가 그려지는 처음의 모습 - 그리고 당분간 이어질 모습 - 안에는 게임 컨트랙트, 게임에서 사용되는 토큰 컨트랙트, 이가 거래되는 탈중앙화 거래소 컨트랙트이 주를 - 대부분 - 차지할 것이다. GXCIO는 이 common case를 “싸고”, “빠르게" 처리할 수 있는 구조로 구현할 것이다.


### 3.2.2. Limitations of EOSIO’s Contract

EOSIO는 3,000tps를 웃도는 속도, 0.5초 confirmation time을 제공하여 Dapp이 실제로 동작가능한 환경을 제공해주었다. 하지만 EOSIO의 자원 가격은 DApp 제공자들이 감당할 수 없을 만큼의 가격을 형성하였고, 이는 EOSIO가 당초 제공하고자 하는 환경에 크게 어긋나는 상황이다. EOSIO를 기반으로 동작하려는 대부분의 dapp들은 자원 할당이라는 기초적인 단계에서 막혀 제품을 제대로 제공하지 못하고 있다.

### 3.2.3. Characteristics of GXC Native Action

GXC는 3.2.1에서 제시했던 논조에서 밝혔던 것처럼, 스마트 컨트랙트에서의 Common Case에 대한 Resource 문제를 시스템의 Native Action으로 제공하여 문제를 풀고자 한다. 빈번한 요청이 예상되는 Native Action은  RAM, CPU, Bandwidth를 사용하는데 있어 아래 서술될 특수한 규칙에 의해 동작할 것이고, 이는 게임개발사의 DApp 개발에 대한 자원의 부담을 최소화해준다.

### 3.2.4. Native Action Rule

이 장에서 기술되는 Native Action을 통해 생성되는 자원은 특수한 유형의 자원으로 계산되며, RAM에 저장되는 형식도 EOSIO의 Multi-index Token 형태에서 벗어난 형태를 따른다. 토큰의 발행 및 전송에 드는 자원은 별도로 할당한 CPU와 RAM을 이용하게 되어 있으며, 네트워크의 특정 부하 이상을 차지않는 이상 3.2.6의 Fee를 제외한 자원은 DApp 개발자나, 사용자에게 전가되지 않는다. 이는 Waves 플랫폼(https://wavesplatform.com/product)에서 값싸게 Token을 제작 및 전송을 지원하는 방식과 유사하다.

### 3.2.5. Type of Native Action
#### 3.2.5.1. Game Contract

게임 개발자는 Account를 Game developer로 등록하고, Game developer로 등록이 완료된 계정을 이용하여 GXCIO에 Game을 Register할 수 있다.

#### 3.2.5.2. Token Model

토큰의 발행, 이동은 GXC 네트워크에서 제일 많은 비중을 차지할 것이다. 토큰은 기 정의된 Preset에(2.1 참조) 따라 편하게 발행되거나, Token Model을 상속받아 게임사가 customizing하여 발행할 수 있다.
 
#### 3.2.5.3. 탈중앙화 거래소(DEX)

탈중앙화 거래소는 시스템 컨트랙트의 일부로써 운영되며, 유저는 토큰과 GXC와의 교환을 탈중앙화 거래소를 통해 즉시, 편하게 진행할 수 있다. 이 탈중앙화 거래소는 토큰만을 소유한 유저가 GXC 없이 토큰의 전송을 가능케 해주는데, 자동으로 전송에 필요한 GXC를 탈중앙화 거래소에서 구매, 토큰을 가능케 해준다.

### 3.2.6. Fees

토큰 전송 등 일부 시스템 컨트랙트의 기능은 CPU, Bandwidth, RAM의 사용에 대한 Staking을 요구하지 않으나, Network 과부하를 막기 위해 수행하는데 작은량의 GXC를 필요로 한다. 이는 리플(XRP) 전송에서 필요한 수수료와 비슷한 역할을 한다고 보면 된다. 해당 GXC는 BP의 Block Producing에 대한 대가의 일부로도 지불된다. 


### 3.2.7. 예외 상황에 대한 컨트롤

Native Action의 자원 사용은 3.2에서 밝힌 방법들을 통해 굉장히 싸고 편하게 기능이 제공돠고, 이에 대한 남용은 3.2.6에 얘기한 최소한의 Fee를 통해 컨트롤하고자 한다. 하지만 네트워크 상황은 언제 급변할지 모르고, 순간적인 트래픽 발생은 EOSIO의 초당 처리 능력을 초과할 수 있다. 이런 예외적인 상황이 발생시, 프로토콜은 기 정의된 Native Action들도 3.4의 방법을 통해 동작하도록 설계되어 이로인해 생기는 문제를 최소화하도록 하려고 한다.



## 3.3. Accounts
### 3.3.1. Permission

![](https://user-images.githubusercontent.com/1560710/44506433-665ca480-a6e1-11e8-94aa-51416d79e344.png)
개발자는 유저에게 자신의 게임에서 사용되는 자산에 대한 권한을 유저에게 요청할 수 있다. 이 권한은 유저의 의중에 따라 언제든 발행 및 회수가 가능하다. 이를 통해 유저는 최소한의 권한만을 게임사에게 위임하여 게임 플레이 도중 UX/UI의 전환없이 게임을 즐길 수 있고, 혹시 모를 자산권의 침해 - 게임사의 해킹으로 인한 키 노출 - 를 최소화할 수 있다.

### 3.3.2. Anonymous Account

GXCIO에 들어오지 않은 유저도 게임을 플레이하고, 토큰을 획득할 수 있어야 한다. Game사는 Anonymous 계정들이 토큰을 가지게 관리할 수 있으며, 추후에 이런 유저가 토큰의 계정 생성 후 그 권리를 claim할 시 해당 토큰을 유저의 계정으로 쉽게 이전할 수 있다.

## 3.4. Make the rare case correct.

GXCIO는 OS이며, 앞에서 말한 Native Action외의 스마트 컨트랙트의 생성 및 실행을 지원한다. 이런 컨트랙트의 실행을 위해서 컨트랙트에 필요한 CPU, Bandwith 및 RAM 자원을 필요한 만큼 할당받아서 사용하게 된다.  이 할당에 대한 정책은 기본적으로 EOSIO에서 채택한 방식을 사용하며, RAM에서 생기는 가격의 폭등은 3.2.1에서 언급된 common case를 해결하는 방식과 4.1.2.2를 통한 지속적인 RAM 증설을 BP의 의무로 함으로 해소가 가능하다.


## 3.5. Sidechain

초기 GXCIO는 메인체인만을 이용해 구성되며, 수십의 게임과 토큰을 지원하기에 충분하다. 하지만 더 많은 게임이 GXCIO와 결합되고, 더 많은 유저들이 네트워크에 들어오면 메인체인만으로는 감당이 힘들어지는 단계에 다다를 것이다.

GXCIO는 Sidechain을 활용하여 확장성 문제를 해결하려고 한다. GXCIO 생태계는 복수의 게임의 트랜잭션으로 이루어지고, 하나하나의 게임은 하나의 계를 이루는 구조로 볼 수 있다. 이는 다수의 블록체인에서 정의하는 Sidechain으로 동작하기 ‘개념적으로' 잘 들어맞는다. 또한 Sidechain을 통해 좀 더 유연한 구조의 게임 -  2.1.3에서 보여주는 - 을 적합하게 만들 수 있을 것이다.

GXC팀은 다양한 방식의 Sidechain을 염두에 두고 있으며 - 현재는 Escrow Pool과 밀접한 관련이 있는 Plasma 및 Plasmacash 를 이용한 방식을 염두에 두고 있다 - 그 구현 양식 및 방법으로는 “GXCIO에 잘 어울리고", “더 게임에 잘 어울리는" 방식을 채용하여 이를 구현하고자 한다.

# 4. Governance

GXCIO는 누구든지 들어오고 나가는 것이 자유로운 퍼블릭 블록체인이다. 생태계 구성원들은  블록체인이 돌아가도록 구성하고, 발전에 관한 의사결정을 하고, 그에 따른 보상을 받는다.

## 4.1. Block Producer
### 4.1.1. 구성

최초의 BP는 13개로 구성되며, 6개월마다 2개씩 추가되어 최종적으로 21개까지 늘어난다. GXC Holder들의 투표로 BP는 선출되며, BP로 선출되지 못한 후보군들은 예비 BP가 되어 BP가 그 역할을 제대로 수행하지 못했을 때 대체 BP의 역할을 한다. 게임 블록체인이라는 특성상 실제 게임을 GameXCoin 블록체인 위에서 구동하는 개발사의 BP참여의 기회를 보장하기 위하여, BP 투표중 50% 정도를 개발사가 가져가도록 유도하고자 한다. 이를 위해 전체 BP의 절반 가까이 - (n-1) / 2 는 일정 수량의 GXC를 에스크로 풀에 예치하여 발행한 게임사 중에서 선정하는 것으로 한다.

### 4.1.2. 역할
#### 4.1.2.1. 블록생성

선출된 BP의 가장 중요한 역할은 Transaction의 내용을 Block에 기록하고, 이를 배포하는 일이다. 블록 생성은 일정한 규칙에 따라 BP들이 수행 및 검증하게 된다.

#### 4.1.2.2. Resource 제공

BP는 GXCIO의 Transaction들이 리소스 부족없이 잘 동작하도록 충분한 Resource를 제공하여야 한다. 특히 RAM은 데이터를 지우지 않는한 계속 저장공간을 차지하는 자원으로, 지속적으로 인프라가 제공이 되어야 건강한 생태계를 유지할 수 있다. 

### 4.1.3. 권한

BP들은 GXCIO의 많은 값들에 대해 논의하고, 변경할 권한을 가진다. 이 권한을 행사하기 위해선 최소 2/3 초과의 BP들이 해당 안에 동의해야 한다.

#### 4.1.3.1. Parameter

GXCIO의 많은 장치들에서 파라미터는 - 가령 Inflation율이라든가 - 네트워크 관계자에게 많은 영향을 끼친다. BP의 합의를 통해, 해당 파라미터의 수치는 변경될 수 있다. 

#### 4.1.3.2. 계정정지

어떤 계정이 해킹에 연루되거나, 블록체인을 어뷰징하는 일은 불행하지만 가끔씩 일어나곤 한다. BP들은 이러한 일에 대해 조사하고, 계정을 정지하는 등의 행위를 할 수 있다.

#### 4.1.3.3. Token Pause for abusing games

BP들의 투표로 메인체인의 주요 파라미터 값이 변경될 수 있다. 또한 BP는 이상행위가 검출된 계정을 동결하거나, 이상 행동이 벌어지는 Token의 입출입을 정지하는 등의 역할을 할 수 있다.

## 4.2. GXC Holders

GXC의 Holder는 다양한 유형이 존재할 수 있다. BP도 GXC Holder이며, 게이밍을 통해 GXC를 획득한 이도 GXC Holder이며, 탈중앙화 거래소나 거래소를 통해 GXC를 획득한 이도 GXC Holder이다. GXC Holder는 GXC를 통해 다양한 행위가 가능한데, 그 중 Governance와 가장 밀접한 관련이 있는 건 GXC를 Staking하여 할 수 있는 Voting이다.

### 4.2.1. Voting

Voting은 GXC를 Staking한 유저라면 누구든지 참여가능하며, 각각의 투표는 독립사건으로 구성된다. 즉 BP투표를 한 유저도 Game 투표에 참가할 수 있다. Staking한 GXC는 투표 후 일정기간이 지나야 출금이 가능하다.

#### 4.2.1.1. Voting for Block Producers

유저는 누가 BP의 역할에 적합할지 투표를 행사할 수 있다. 유저는 최대 [10 * n /7] (n은 BP의 개수)의 BP에게 동시에 투표할 수 있으며, 이 투표의 결과로 BP 및 예비 BP가 선출된다. 

#### 4.2.1.2. Voting for Games

유저는 플레이한 기록이 된 게임에 대해 투표를 할 수 있다. 이 투표의 결과를 정해진 산술을 통해 게임별로 순위가 메겨지며, 이 순위에 따라 4.3의 Inflation의 Gaming 보상이 게임별로 차등 지급된다. 게임 순위로직은 1) 투표에 참여한 유저 수 2) Staking된 GXC의 양 3) 이전 라운드 순위 등을 변수로 하여 정해진다. 

## 4.3. Work Proposal

GXCIO가 게임 블록체인으로 지속적으로 성장하기 위해선 블록체인과 이를 활용한 Product의 지속적인 개발 및 발전이 있어야 한다. Work Proposal은 이러한 선순환이 가능하게 하기 위한 구조이며, 기본적으로 Dash Proposal(https://proposal.dash.org/) 의 형태를 가질 것이다. 

## 4.4. Inflation

GXC는 정해진 Inflation양에 따라 지속적으로 발행되며, 이 발행된 양은 네트워크 관계자들에게 분배된다. 최초의 Inflation율은 5%로 설정되며 이 Inflation율은 BP들의 논의를 통해 조절 될 수 있다.

### 4.4.1. Inflation의 분배

Inflation은 네트워크에 기여한 관계자들에게 분배된다. 분배의 로직 및 수치는 운영 중에 BP들의 합의로 변경이 가능하다. 보상은 Block Producing에 대한 BP에 대한 보상, 4.2.1.의 Voting에 대한 보상, 2.1.2.1의 게임 투표에 결과에 의한 보상, 4.3의 GXCIO의 발전을 위한 Work Proposal 보상으로 나뉘며, 초기 보상률은 각 보상 당 1%, 1%, 2%, 1%(전체 5% 기준)으로 구성된다.

# 5. Products

앞선 요소들은 GXCIO의 핵심 축을 담당한다면, 이를 각 사용자가 쉽게 접근이 가능하도록 하는 도구는 Products이다. Products는 유저를 위한 GXC.World, 개발자를 위한 Dev.World, 블록체인의 사용성을 돕는 Chain.World로 구성된다. 

## 5.1. GXC.World

 GXC World는 유저와 GXCIO와의 가교 역할을 해주는 공간이다. 이 공간을 통해 유저는 보다 편하고, 직관적으로 GXCIO의 Ecosystem에 참여할 수 있다.

### 5.1.1. Wallet

유저는 본인 계정에 대한 관리를 GXC.World를 통해 할 수 있다. 이는 본인 계정의 잔고확인, GXC 및 토큰 전송 등의 기본적인 기능 및 GXC Staking을 통한 게임 투표, BP 투표 및 토큰을 이용한 GXC Claim기능을 수행 할 수 있다. 

### 5.1.2. Gaming Portal
게이머는 GXC.World를 통해 게임에 관한 기능을 수행할 수 있다. 유저의 게이밍 기록, 즐겨하는 게임 및 추천 게임 등을 볼 수 있으며, GXC를 이용한 게임 구매 등의 기능도 제공된다. 

### 5.1.3. DEX

유저는 DEX를 사용하여 언제든지 P2P로 자신의 자산을 GXC 및 토큰으로 교환 가능하다. 

## 5.2. Dev.World

Dev.World는 개발자와 GXCIO와의 가교 역할을 하는 공간이다. 개발자는 이 공간을 활용하여 쉽게 게임배포, 토큰 제작, 이벤트 등의 기능을 사용할 수 있다.
또한 플랫폼별 SDK 및 도큐먼트를 제공하여 게임과 GXCIO와의 연동 용이하게 해준다.

### 5.2.1. 관리공간

블록체인에 직접접근하지 않으면서, 게임 관리에 대한 기능을 제공하는 공간이다. 개발자는 개발자 계정으로의 전환, 게임관리, 토큰관리, 이벤트 관리 기능을 웹상에서 쉽게 사용하여 본인의 게임을 제어할 수 있다.

### 5.2.2. 개발 도구

GXCIO와 연동된 게임을 개발하기 위해선 이를 위한 SDK가 필수적이다. 클라이언트 레벨에서는 Unity, Unreal Engine, Javascript 등 게임에서 주로 사용되는 엔진 및 언어를 위한 SDK가 제공되며, 각 언어별로 서버에서 Chain API Call을 위한 SDK도 같이 제공된다.

## 5.3. Chain.World 

Chain.World는 블록체인 정보를 쉽게 조회할 수 있는 공간이다. Block의 생성, 현재 라운드의 BP 및 예비 BP 목록, Block 및 Transaction 조회가 가능하다. 또한 게임 및 토큰의 등록, GXC 와 토큰의 이동 등의 정보들도 쉽게 조회가 가능하다.

# 6. Summary

GameXCoin은 블록체인 기술을 이용하여 게임을 연결하고, 거기서 만들어지는 가치를 네트워크 이해 관계자들에게 제공하여 그 가치를 더욱 높이고자 한다. GameXCoin은 궁극적으로 게임 공급 플랫폼이자, 게임 내 재화를 위한 거래소이자, 게이머들이 게임을 더 잘 놀 수 있는 장이 되고자 한다. 이 글은 이러한 GameXCoin의 청사진을 담았기에 청서라 이름 짓는다.
