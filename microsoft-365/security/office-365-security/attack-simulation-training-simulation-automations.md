---
title: 공격 시뮬레이션 교육을 위한 시뮬레이션 자동화
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 관리자는 Microsoft Defender for Office 365 Plan 2에서 지정된 조건이 충족될 때 실행되는 특정 기술 및 페이로드를 포함하는 자동화된 시뮬레이션을 만드는 Office 365 있습니다.
ms.technology: mdo
ms.openlocfilehash: a6612a14a4a583cf3b61cf7b678fbdc1d1055dc6
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60662055"
---
# <a name="simulation-automations-for-attack-simulation-training"></a>공격 시뮬레이션 교육을 위한 시뮬레이션 자동화

**Microsoft** [Defender for Office 365 요금제 2에 적용](defender-for-office-365.md)

공격 시뮬레이션 교육에 대한 시작 정보는 공격 시뮬레이션 교육 사용 [시작을 참조하세요.](attack-simulation-training-get-started.md)

시뮬레이션 자동화를 만들 수 있는 경우 다음 단계를 수행합니다.

1. 의 Microsoft 365 Defender 포털에서 전자 메일 & 공격 시뮬레이션 <https://security.microsoft.com/>  \> **교육** \> **시뮬레이션 자동화 탭으로 이동하세요.**

   시뮬레이션 자동화 **탭으로** 직접 이동하기 위해 를 <https://security.microsoft.com/attacksimulator?viewid=simulationautomation> 사용합니다.

2. 시뮬레이션 **자동화 탭에서** 시뮬레이션 ![ 만들기 아이콘을 선택합니다.](../../media/m365-cc-sc-create-icon.png) **시뮬레이션을 생성합니다.**

   ![포털의 공격 시뮬레이션 교육에서 시뮬레이션 자동화 탭에 시뮬레이션 단추를 Microsoft 365 Defender.](../../media/attack-sim-training-sim-automations-create.png)

3. 만들기 마법사가 열립니다. 이 문서의 나머지부분에서는 페이지 및 페이지에 포함된 설정에 대해 설명합니다.

> [!NOTE]
> 시뮬레이션 만들기 마법사 중 어느 시점에서든 저장 및 닫기 를 클릭하여 진행률을 저장하고 나중에 시뮬레이션을 계속 구성할 수 있습니다.  불완전한 시뮬레이션의  상태  값은 시뮬레이션 탭에 **임시로** 표시됩니다. 시뮬레이션을 선택하고 시뮬레이션 편집 아이콘을 클릭하여 떠날 위치를 선택할 ![ 수 있습니다.](../../media/m365-cc-sc-edit-icon.png) **simulation.##** 이름을 편집하고 시뮬레이션을 설명합니다.

## <a name="name-and-describe-the-simulation-automation"></a>시뮬레이션 자동화 이름 및 설명

자동화 **이름 페이지에서** 다음 설정을 구성합니다.

- **이름:** 시뮬레이션을 설명하는 고유한 이름을 입력합니다.
- **설명:** 시뮬레이션에 대한 선택적 자세한 설명을 입력합니다.

작업을 마친 후 **다음** 을 클릭합니다.

## <a name="select-one-or-more-social-engineering-techniques"></a>하나 이상의 소셜 엔지니어링 기술 선택

소셜 **엔지니어링** 기술 선택 페이지에서 [MITRE ATT 및 ®CK&](https://attack.mitre.org/techniques/enterprise/)프레임워크에서 큐레이터된 사용 가능한 소셜 엔지니어링 기술 중&선택합니다. 다양한 기술에 대해 다양한 페이로드를 사용할 수 있습니다. 다음과 같은 소셜 엔지니어링 기술을 사용할 수 있습니다.

- **자격 증명 수집:** 입력란이 있는 잘 알려진 웹 사이트로 사용자를 연결하여 사용자 이름과 암호를 제출하여 자격 증명을 수집하려고 합니다.
- **맬웨어 첨부** 파일: 메시지에 악성 첨부 파일을 추가합니다. 사용자가 첨부 파일을 열면 공격자가 대상의 장치를 손상시킬 수 있도록 임의의 코드가 실행됩니다.
- **첨부 파일 링크:** 자격 증명 수집 하이브리드의 유형입니다. 공격자는 전자 메일 첨부 파일에 URL을 삽입합니다. 첨부 파일 내의 URL은 자격 증명 수집과 동일한 기술을 따르게 됩니다.
- **맬웨어** 링크: 잘 알려진 파일 공유 서비스에 호스트된 파일에서 임의 코드를 실행합니다. 사용자에게 전송된 메시지에는 이 악성 파일에 대한 링크가 포함되어 있습니다. 파일을 열고 공격자가 대상의 장치를 손상시킬 수 있도록 합니다.
- **드라이브-BY URL:** 메시지의 악의적인 URL은 사용자가 자동으로 실행되거나 사용자 장치에 코드 코드를 설치하는 친숙한 웹 사이트로 이동됩니다.

설명에서 세부  정보 보기 링크를 클릭하면 기술 및 해당 기술로 인해 수행된 시뮬레이션 단계를 설명하는 세부 정보 플라이아웃이 열립니다.

![소셜 엔지니어링 기술 선택 페이지에서 자격 증명 수집 기술에 대한 플라이아웃에 대한 세부 정보를 제공합니다.](../../media/attack-sim-training-simulations-select-technique-sim-steps.png)

작업을 마친 후 **다음** 을 클릭합니다.

## <a name="select-payloads"></a>페이로드 선택

페이로드 **선택 페이지에서** 다음 옵션 중 하나를 선택합니다.

- **수동으로 선택**
- **임의화**

임의화 **를** 선택하면 이 페이지에서 구성할 것이 없습니다.를 선택하면 **다음을** 클릭하여 계속합니다.

수동으로 **선택을 선택하는** 경우 목록에서 하나 이상의 페이로드를 선택해야 합니다. 다음 세부 정보가 표시되어 선택에 도움이 됩니다.

- **페이로드 이름**
- **기술:** 이전 페이지에서 선택한 기술당 하나의 페이로드로 선택해야 합니다.
- **언어:** 페이로드 콘텐츠의 언어입니다. Microsoft의 페이로드 카탈로그(전역)는 10개 이상의 언어로 페이로드를 제공하 고 필터링할 수도 있습니다.
- **클릭 비율:** 이 페이로드를 클릭한 사용자 수입니다.
- **예측된** 손상율: 이 페이로드에 의해 손상될 Microsoft 365 비율을 예측하는 전체 페이로드에 대한 기록 데이터입니다.
- **실행된 시뮬레이션은** 이 페이로드가 다른 시뮬레이션에 사용된 횟수를 계산합니다.

검색 ![ 아이콘](../../media/m365-cc-sc-search-icon.png) **검색** 상자에 페이로드 이름의 일부를 입력하고 Enter를 눌러 결과를 필터링할 수 있습니다.

필터를 **클릭하면** 다음과 같은 필터를 사용할 수 있습니다.

- **복잡성:** 가능한 공격(맞춤법 오류, 긴급성 등)을 나타내는 페이로드의 지표 수에 따라 계산됩니다. 더 많은 지표가 공격으로 식별하기 더 쉬우며 복잡성이 낮을 수 있습니다. 사용 가능한 값은 다음과 같습니다.
  - **낮음**
  - **Medium**
  - **High**
- **원본:** 페이로드가 조직에서 만들어지거나 Microsoft의 기존 페이로드 카탈로그에 일부인지 여부를 나타냅니다. 유효한 값은 다음과 같습니다.
  - **Global**
  - **테넌트**
  - **모두**
- **언어:** 사용 가능한 값은 **영어,** **스페인어,** **독일어,** **일본어,** **프랑스어,** **포르투갈어,** **네덜란드어,** **이탈리아어,** **스웨덴어,** 중국어(간체) , **노르웨이어 Bokmål,** **폴란드어,** 러시아어, **핀란드어,** **한국어,** **터키어,** **헝가리어,히브리어,**  **태국어,** **아랍어,** **베트남어,** 슬로바키아어  ****, **그리스어,** **인도네시아어,** **루마니아어,** **콜로베니아어,** **크로아티아어,** 카탈로니아어 및 **기타**.
- **태그 추가**
- 테마별 필터링 **:** 사용 가능한 값은 계정 **활성화,** 계정 **확인,** **청구,** 메일 **정리,** **문서 수신,** **경비,** 팩스,  **재무** **보고서,** 받는 메시지, **송장** **,** 받은 항목, 로그인 **알림,** 메일 **수신,** **암호,** **결제,** 급여, 개인 설정된 **제안,** **Quarantine**, **원격 작업,** **메시지 검토,** **보안 업데이트,** **서비스** 일시 중단, **서명 필요,** 사서함 **저장소** 업그레이드 사서함 확인, **음성 메일** 및 **기타**.
- 브랜드별 필터 **:** 사용할 수 있는 값은 **American Express,** **Capital One,** **DHL,** **DocuSign**, **Dropbox**, Facebook , **First** **American**, **Microsoft**, **Microsoft ,의 경우,** **Scotiabank,** **SendGrid**, **Stewart Title**, **Tesco**, **Wells Fargo,** **Syrinx Cloud** 및 **기타입니다.**
- 산업 필터 : 사용 가능한 값은 뱅킹, **비즈니스** 서비스, **소비자** 서비스, **교육,** **에너지,** **구성,** **컨설팅,** **금융** 서비스, **정부,** 병원, 보험, **법률,** **Courier 서비스,** **IT,** **의료,** **제조,** **소매,** **Telecom,** 부동산 **,** 금융 서비스입니다.    및 **기타**.
- **현재 이벤트:** 사용 가능한 값은 **예 또는 아니요입니다.** 
- **논란:** 사용 가능한 값은 **예 또는 아니요입니다.** 

필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**

이름을 클릭하여 목록에서 페이로드를 선택하면 페이로드에 대한 세부 정보가 플라이아웃에 표시됩니다.

- 개요 **탭에는** 페이로드에 대한 예제 및 기타 세부 정보가 포함되어 있습니다.
- **시작된 시뮬레이션 탭에는** **시뮬레이션** 이름, **클릭률,** 손상된 비율 및 **동작이 포함되어 있습니다.**

![웹 포털의 공격 시뮬레이션 교육에서 페이로드 세부 Microsoft 365 Defender 플라이아웃합니다.](../../media/attack-sim-training-simulations-select-payload-details.png)

작업을 마친 후 **다음** 을 클릭합니다.

## <a name="target-users"></a>대상 사용자

대상 **사용자 페이지에서** 시뮬레이션을 받을 사용자를 선택합니다. 다음 설정 중 하나를 구성합니다.

- **조직의 모든 사용자 포함:** 영향을 받는 사용자는 10개 목록에 표시됩니다. 사용자 목록 바로  아래에 **있는 다음** 및 이전 단추를 사용하여 목록을 스크롤할 수 있습니다. 검색 아이콘을 ![ 사용할 수도 있습니다.](../../media/m365-cc-sc-search-icon.png) **페이지의** 검색 아이콘을 사용하여 영향을 받는 사용자를 찾을 수 있습니다.
- **특정 사용자 및 그룹만 포함:** 다음 옵션 중 하나를 선택합니다.
  - ![사용자 아이콘 추가](../../media/m365-cc-sc-create-icon.png) **사용자 추가:**  나타나는 사용자 추가 플라이아웃에서 다음 기준에 따라 사용자 및 그룹을 찾을 수 있습니다.
    - **사용자 또는 그룹:** 사용자 및 그룹 ![ 검색 아이콘에서](../../media/m365-cc-sc-search-icon.png) **사용자 및 그룹 검색** 상자에 사용자  또는  그룹의 이름 또는 전자 메일 주소의 일부를 입력한 다음 Enter를 누를 수 있습니다. 결과의 일부 또는 전체를 선택할 수 있습니다. 완료되면 x 사용자 **추가를 클릭합니다.**

      > [!NOTE]
      > 필터 **추가 단추를** 클릭하여 범주별로 사용자 필터링 옵션으로 돌아가면 검색 결과에서 선택한 모든 사용자 또는 그룹이 지워지게 됩니다. 

    - **범주별로 사용자** 필터링: 다음 옵션 중 없음, 일부 또는 모두에서 선택합니다.
      - **제안된 사용자 그룹:** 다음 값에서 선택합니다.
        - **모든 제안된 사용자 그룹**
        - **지난 3개월 동안 시뮬레이션 대상이 아닌 사용자**
        - **반복되는 가해자**
      - **부서:** 다음 옵션을 사용하세요.
        - **검색**: ![ 부서로 검색 아이콘에서.](../../media/m365-cc-sc-search-icon.png) **부서별로 검색** 상자에 Department 값의 일부를 입력한 다음 Enter를 누를 수 있습니다. 결과의 일부 또는 전체를 선택할 수 있습니다.
        - 모든 **부서 선택**
        - 기존 Department 값을 선택합니다.
      - **제목:** 다음 옵션을 사용하세요.
        - **검색**: ![ 제목으로 검색 아이콘에서](../../media/m365-cc-sc-search-icon.png) **제목으로 검색** 상자에 제목 값의 일부를 입력한 다음 Enter를 누를 수 있습니다. 결과의 일부 또는 전체를 선택할 수 있습니다.
        - 모든 **제목 선택**
        - 기존 Title 값을 선택합니다.

      ![웹 사이트 포털의 공격 시뮬레이션 교육에서 대상 사용자 페이지의 Microsoft 365 Defender.](../../media/attack-sim-training-simulations-target-users-filter-by-category.png)

      조건을 식별하면 영향을 받는 사용자가 표시되는 사용자  목록 섹션에 표시될 수 있습니다. 여기서 검색된 받는 사람을 일부 또는 모두 선택할 수 있습니다.

      완료되면 **적용(x)을** 클릭하고 x 사용자 **추가를 클릭합니다.**

  주 대상 **사용자** 페이지에서 다시 검색 아이콘을 사용할 ![ 수 있습니다.](../../media/m365-cc-sc-search-icon.png) **영향을** 받는 사용자를 찾는 검색 상자입니다. 삭제 ![ 아이콘을 클릭할 수도 있습니다.](../../media/m365-cc-sc-delete-icon.png) **삭제를** 사용하여 특정 사용자를 제거합니다.

- ![가져오기 아이콘.](../../media/m365-cc-sc-create-icon.png) **가져오기:** 열리면 대화 상자에서 한 줄에 전자 메일 주소가 하나씩 포함된 CSV 파일을 지정합니다.

  CSV 파일 선택을 찾은 후 사용자 목록을 가져와서 대상 사용자 **페이지에** 표시됩니다. 검색 ![ 아이콘을 사용할 수 있습니다.](../../media/m365-cc-sc-search-icon.png) **영향을** 받는 사용자를 찾는 검색 상자입니다. 삭제 ![ 아이콘을 클릭할 수도 있습니다.](../../media/m365-cc-sc-delete-icon.png) **삭제를** 사용하여 특정 사용자를 제거합니다.

작업을 마친 후 **다음** 을 클릭합니다.

## <a name="assign-training"></a>교육 할당

교육 **할당 페이지에서** 시뮬레이션에 대한 교육을 할당할 수 있습니다. 교육을 통과하는 직원은 유사한 공격에 덜 덜 공격하기 까다로우며 각 시뮬레이션에 대한 교육을 할당하는 것이 좋습니다. 다음과 같은 설정을 사용할 수 있습니다.

- **교육 콘텐츠 기본 설정 선택:** 다음 옵션 중 하나를 선택합니다.
  - **Microsoft 교육 환경:** 다음과 같은 관련 옵션을 구성하는 기본값입니다.
    - 다음 옵션 중 하나를 선택합니다.
      - **교육 할당:** 이것이 기본값이자 권장 값입니다. 사용자의 이전 시뮬레이션 및 교육 결과를 기반으로 교육을 할당하며 마법사의 다음 단계에서 선택을 검토할 수 있습니다.
      - **교육 과정 및** 모듈을 바로 선택: 이 값을 선택하면 마법사의 다음 단계에서 사용 가능한 모든 과정 및 모듈뿐만 아니라 권장 콘텐츠를 계속 볼 수 있습니다.
    - **기한:** 다음 값 중 하나를 선택하십시오.
      - **시뮬레이션이 종료된 후 30일**: 이 값은 기본값입니다.
      - **시뮬레이션 종료 후 15일**
      - **시뮬레이션이 종료된 후 7일**
  - **사용자 지정 URL로 리디렉션:** 이 값에는 다음과 같은 관련 옵션을 구성할 수 있습니다.
    - **사용자 지정 교육** URL(필수)
    - **사용자 지정 교육** 이름(필수)
    - **사용자 지정 교육 설명**
    - **사용자 지정 교육 기간(분)**: 기본값은 0으로, 교육에 지정된 기간이 없음을 나타냅니다.
    - **기한:** 다음 값 중 하나를 선택하십시오.
      - **시뮬레이션이 종료된 후 30일**: 이 값은 기본값입니다.
      - **시뮬레이션 종료 후 15일**
      - **시뮬레이션이 종료된 후 7일**
  - **교육 없음:** 이 값을 선택하면 방문 페이지 페이지로  이동하는 다음 단추만 페이지에서 선택할 [**수**](#landing-page) 있습니다.

![포털의 공격 시뮬레이션 교육에서 교육 할당 페이지에 권장되는 교육을 Microsoft 365 Defender 추가합니다.](../../media/attack-sim-training-simulations-assign-training-add-recommended-training.png)

### <a name="training-assignment"></a>교육 배정

> [!NOTE]
> **교육 배정** 페이지는 **Microsoft** 교육 환경을 선택한 경우 이전 페이지에서 교육 과정 및 모듈을 \> **선택해야만** 사용할 수 있습니다.

교육 **할당 페이지에서** 교육 추가 아이콘을 클릭하여 시뮬레이션에 추가할 ![ 교육을 선택합니다.](../../media/m365-cc-sc-create-icon.png) **교육을 추가합니다.**

나타나는 **교육 플라이아웃** 추가에서 사용 가능한 다음 탭에서 사용할 교육을 선택할 수 있습니다.

- **권장** 탭: 시뮬레이션 구성에 따라 권장되는 기본 제공 교육을 보여줍니다. 이전 페이지에서 교육 할당을 선택한 경우 할당된 동일한 교육입니다. 
- **모든 교육 탭:** 사용 가능한 모든 기본 제공 교육을 보여줍니다.

  각 교육에 대해 다음 정보가 표시됩니다.

  - **교육 이름**
  - **Source**: 값은 **Global입니다.**
  - **기간(최소)**
  - **미리** 보기: 미리 보기 **단추를** 클릭하여 교육을 봐야 합니다.

  검색 ![ 아이콘](../../media/m365-cc-sc-search-icon.png) **검색** 상자에 교육 이름의 일부를 입력하고 Enter를 눌러 현재 탭에서 결과를 필터링할 수 있습니다.

  현재 탭에서 포함할 모든 교육을 선택하고 추가를 **클릭합니다.**

기본 교육 **배정** 페이지에는 선택한 교육이 표시됩니다. 각 교육에 대해 다음 정보가 표시됩니다.

- **교육 이름**
- **원본**
- **기간(최소)**

목록의 각 교육에 대해 할당 대상 열에서 값을 선택하여 교육을 받을 **대상을 선택해야** 합니다.

- **모든 사용자**

  또는 다음 값 중 하나 또는 둘 다를 사용합니다.

- **클릭한 페이로드**
- **손상된 경우**

표시된 교육을 사용하지 않는 경우 삭제 ![ 아이콘을 클릭합니다.](../../media/m365-cc-sc-delete-icon.png) **삭제**.

![포털에서 공격 시뮬레이션 교육의 Microsoft 365 Defender 페이지입니다.](../../media/attack-sim-training-training-assignment.png)

작업을 마친 후 **다음** 을 클릭합니다.

### <a name="landing-page"></a>방문 페이지

방문 **페이지 페이지에서** 사용자에게 교육 방문 페이지를 구성합니다. 다음과 같은 설정을 사용할 수 있습니다.

- **헤더**
- **본문**

기본값을 수락하거나 사용자 지정할 수 있습니다.

작업을 마친 후 **다음** 을 클릭합니다.

## <a name="simulation-schedule"></a>시뮬레이션 일정

시뮬레이션 **일정 페이지에서** 다음 값 중 하나를 선택합니다.

- **임의로** 선택: 다음 페이지에서 일정을 선택해야 하지만 시뮬레이션은 일정에 따라 임의로 실행됩니다.
- **고정**

작업을 마친 후 **다음** 을 클릭합니다.

## <a name="schedule-details"></a>세부 정보 예약

일정 세부 정보 **페이지에** 표시하는 내용은 이전 페이지에서 **임의** 또는 고정을 선택 여부에 따라 결정됩니다. 

- **임의로** 구성: 다음 설정을 사용할 수 있습니다.
  - **시뮬레이션 시작** 섹션: 다음 설정을 구성합니다.
    - **시뮬레이션을 시작할 날짜 선택**
  - **Simulation scoping** 섹션: 다음 설정을 구성합니다.
    - **시뮬레이션이** 시작될 수 있는 주 중 일을 선택합니다. 한 주 중 하나 이상을 선택합니다.
    - **시작 날짜와** 종료 날짜 사이에 시작할 수 있는 최대 시뮬레이션 수를 입력합니다. 1에서 10 사이의 값을 입력합니다.
    - **보내기 시간 임의화:** 보내기 시간을 임의로 설정하려면 이 설정을 선택합니다.
  - **시뮬레이션 끝 섹션:** 다음 설정을 구성합니다.
    - **시뮬레이션을 종료할 날짜 선택**

- **고정:** 다음 설정을 사용할 수 있습니다.
  - **시뮬레이션 시작** 섹션: 다음 설정을 구성합니다.
    - **시뮬레이션을 시작할 날짜 선택**
  - **시뮬레이션 재발 섹션:** 다음 설정을 구성합니다.
    - **시뮬레이션을** 매주 또는 월별 시작하려면 선택: 다음 값 중 하나를 선택합니다.
      - **Weekly**: 이 값은 기본값입니다.
      - **매월**
    - **시뮬레이션이** 몇 주에 얼마나 자주 재발할지 입력합니다. 1주에서 99주까지의 값을 입력합니다.
    - **시뮬레이션을 시작할 주 중 선택한 날을 선택합니다.**
  - **시뮬레이션 끝 섹션:** 다음 값 중 하나를 선택합니다.
    - **시뮬레이션을 종료할 날짜 선택**
    - **종료하기** 전에 실행할 시뮬레이션 발생 횟수를 입력합니다. 1에서 10까지의 값을 입력합니다.

작업을 마친 후 **다음** 을 클릭합니다.

## <a name="launch-details"></a>시작 세부 정보

시작 **세부 정보 페이지에서** 자동화에 대해 다음과 같은 추가 설정을 구성합니다.

- **자동화 내에서** 시뮬레이션에서 고유한 페이로드 사용: 기본적으로 이 설정은 선택되지 않습니다.
- **대상 반복 가해자:** 기본적으로 이 설정은 선택되어 있지 않습니다. 이 옵션을 선택하면 나타나는 다음 설정을 구성합니다.
  - **이 자동화 내에서** 사용자를 대상으로 할 수 있는 최대 횟수를 입력합니다. 1에서 10까지의 값을 입력합니다.
- **웹앱에서** 사용자의 현재 표준 시간대 설정에 따라 시뮬레이션 Outlook 보내기: 기본적으로 이 설정은 선택되어 있지 않습니다.
- **드라이브 간** 기술 수집 페이지 표시 : 이 설정은 하나 이상의 소셜 엔지니어링 기술 선택 페이지에서 **URL로** 드라이브를 선택한 경우 **[사용할 수](#select-one-or-more-social-engineering-techniques)** 있습니다. 기본적으로 설정은 입니다( 아이콘을 ![ 토글합니다. ](../../media/scc-toggle-on.png) ).

## <a name="review-simulation-automation"></a>시뮬레이션 자동화 검토

시뮬레이션 **자동화 검토 페이지에서** 시뮬레이션 자동화의 세부 정보를 검토할 수 있습니다.

각 섹션에서 **편집** 선택하여 섹션 내의 설정을 수정할 수 있습니다. 또는 **뒤로** 를 클릭하거나 마법사에서 특정 페이지를 선택할 수 있습니다.

작업을 마쳤으면 **제출** 을 클릭합니다.
