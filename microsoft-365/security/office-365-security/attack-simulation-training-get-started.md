---
title: 공격의 신나는 교육 사용 시작
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 관리자는 공격 시뮬레이션 교육을 사용하여 Microsoft 365 E5 계획 2 조직용 Microsoft Defender에서 시뮬레이션된 피싱 및 암호 Office 365 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e3a1be88cb1666f689b4482684823ff09fc39fed
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60180995"
---
# <a name="get-started-using-attack-simulation-training"></a>공격의 신나는 교육 사용 시작

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Microsoft** [Defender for Office 365 요금제 2에 적용](defender-for-office-365.md)

조직에 위협 Microsoft 365 E5 및 대응 기능이 포함된 Office 365 계획 2용 [](office-365-ti.md)Microsoft Defender 또는 Microsoft Defender가 있는 경우 Microsoft 365 Defender 포털에서 공격 시뮬레이션 교육을 사용하여 조직에서 실제 공격 시나리오를 실행할 수 있습니다. 이러한 시뮬레이션된 공격은 실제 공격이 아래쪽에 영향을 미치기 전에 취약한 사용자를 식별하고 찾는 데 도움이 될 수 있습니다. 자세한 내용은 이 문서를 읽어 보아야 합니다.

> [!NOTE]
> 공격 시뮬레이션 교육은 Microsoft Defender for Office 365 공격 시뮬레이터에 설명된 이전 공격 시뮬레이터 v1 환경을 [Office 365.](attack-simulator.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용

- Microsoft 365 Defender 포털을 열려면 <https://security.microsoft.com>(으)로 이동합니다. 공격 시뮬레이션 교육은 전자 **메일** 및 공동 작업 공격 시뮬레이션 \> **교육에서 사용할 수 있습니다.** 공격 시뮬레이션 교육으로 직접 이동하기 위해 를 를 를 <https://security.microsoft.com/attacksimulator> 습니다.

- 여러 Microsoft 365 구독의 공격 시뮬레이션 교육 가용성에 대한 자세한 내용은 Microsoft [Defender for Office 365 참조하세요.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

- 이 문서의 절차를 **수행하려면** Azure Active Directory 사용 권한을 할당해야 합니다. 특히, 다음 역할 중 하나의 구성원이 해야 합니다.
  - **조직 관리**
  - **보안 관리자**
  - **공격 시뮬레이션 관리자:** 공격 시뮬레이션 캠페인의 모든 측면을 만들고 <sup>\*</sup> 관리합니다.
  - **공격 페이로드 작성자:** 관리자가 나중에 시작할 수 있는 공격 <sup>\*</sup> 페이로드를 생성합니다.

  <sup>\*</sup>Microsoft 365 Defender 포털에서 이 역할에 사용자를 추가하는 것은 현재 지원되지 않습니다.

  자세한 내용은 Microsoft 365 Defender [포털의](permissions-microsoft-365-security-center.md) 사용 권한 또는 관리자 역할 [정보를 참조하세요.](../../admin/add-users/about-admin-roles.md)

- 공격 시뮬레이션 교육을 위한 해당 PowerShell cmdlet은 없습니다.

- 공격 시뮬레이션 및 교육 관련 데이터는 다른 고객 데이터와 함께 Microsoft 365 저장됩니다. 자세한 내용은 데이터 [Microsoft 365 참조하세요.](../../enterprise/o365-data-locations.md) 공격 시뮬레이션은 NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN, KOR, BRA, LAM, CHE, NOR, ZAF, ARE 및 DEU 지역에서 사용할 수 있습니다.

  > [!NOTE]
  > NOR, ZAF, ARE 및 DEU는 최신 추가입니다. 보고된 전자 메일 원격 분석을 제외한 모든 기능을 이러한 지역에서 사용할 수 있습니다. 이를 사용하도록 설정하기 위해 작업 중입니다. 보고된 전자 메일 원격 분석이 사용 가능해지는 즉시 고객에게 알릴 것입니다. 

- 2021년 6월 15일 현재, 공격 시뮬레이션 교육은 GCC. 조직에서 정부용 G5 Office 365 GCC 또는 Microsoft Defender for Office 365(계획 2)를 사용하는 경우 Microsoft 365 Defender 포털에서 공격 시뮬레이션 교육을 사용하여 이 문서에 설명된 바와 같이 조직에서 실제 공격 시나리오를 실행할 수 있습니다. 공격 시뮬레이션 교육은 High 또는 DoD 환경에서는 GCC 없습니다.

> [!NOTE]
> 공격 시뮬레이션 교육은 평가판으로 E3 고객에게 일부 기능을 제공합니다. 평가판 제품에는 자격 증명 수집 페이로드를 사용하는 능력과 'ISA 피싱' 또는 '대량 시장 피싱' 교육 환경을 선택하는 능력이 포함되어 있습니다. 다른 기능은 E3 평가판 제공에 참여하지는 합니다.

## <a name="simulations"></a>시뮬레이션

*피싱은* 합법적인 보낸 사람이나 신뢰할 수 있는 보낸 사람이 보낸 것으로 나타나는 메시지의 중요한 정보를 도용하려는 전자 메일 공격의 일반적인 용어입니다. *피싱은* 소셜 엔지니어링으로 분류하는 기술의 하위 _집합의 일부입니다._

공격 시뮬레이션 교육에서는 여러 유형의 소셜 엔지니어링 기술을 사용할 수 있습니다.

- **자격 증명 수집:** 공격자가 URL이 포함된 메시지를 받는 사람에게 보냅니다. 받는 사람이 URL을 클릭하면 일반적으로 사용자에게 사용자 이름과 암호를 묻는 대화 상자가 표시되는 웹 사이트로 이동됩니다. 일반적으로 대상 페이지는 사용자에 대한 트러스트 구축을 위해 잘 알려진 웹 사이트를 나타내기 위한 것입니다.

- **맬웨어 첨부** 파일: 공격자가 첨부 파일이 포함된 메시지를 받는 사람에게 보냅니다. 받는 사람이 첨부 파일을 열면 사용자의 장치에서 임의의 코드(예: 매크로)를 실행하여 공격자가 추가 코드를 설치하거나 추가 엔렌치 자체를 설치하도록 합니다.

- **첨부 파일 링크:** 자격 증명 수집의 하이브리드입니다. 공격자는 첨부 파일 내부의 URL이 포함된 메시지를 받는 사람에게 보냅니다. 받는 사람이 첨부 파일을 열고 URL을 클릭하면 일반적으로 사용자에게 사용자 이름과 암호를 묻는 대화 상자가 표시되는 웹 사이트로 이동됩니다. 일반적으로 대상 페이지는 사용자에 대한 트러스트 구축을 위해 잘 알려진 웹 사이트를 나타내기 위한 것입니다.

- **맬웨어에** 대한 링크: 공격자는 잘 알려진 파일 공유 사이트의 첨부 파일에 대한 링크가 포함된 메시지를 받는 사람에게 보냅니다(예: SharePoint Online 또는 Dropbox. 받는 사람이 URL을 클릭하면 첨부 파일이 열리며 사용자의 장치에서 임의의 코드(예: 매크로)가 실행됩니다. 이를 통해 공격자가 추가 코드를 설치하거나 추가 코드를 직접 설치하도록 할 수 있습니다.

- **드라이브-URL:** 공격자가 URL이 포함된 메시지를 받는 사람에게 보냅니다. 받는 사람이 URL을 클릭하면 백그라운드 코드를 실행하는 웹 사이트로 이동됩니다. 이 백그라운드 코드는 받는 사람에 대한 정보를 수집하거나 장치에 임의 코드를 배포하려고 시도합니다. 일반적으로 대상 웹 사이트는 손상된 잘 알려진 웹 사이트 또는 잘 알려진 웹 사이트의 복제본입니다. 웹 사이트에 대해 잘 알고 있는 경우 링크를 클릭하는 것이 안전한지 사용자에게 확신할 수 있습니다. 이 기술을 워터홀 _공격(watering hole attack)라고도 합니다._

> [!NOTE]
> 피싱 캠페인에서 URL을 사용하기 전에 지원되는 웹 브라우저에서 시뮬레이트된 피싱 URL의 가용성을 확인합니다. 항상 이러한 시뮬레이션 URL을 허용하기 위해 많은 URL 신뢰도 공급업체와 협력하고 있는 동안 항상 전체 범위가 있는 것은 아니며(예: Google 금고 검색). 대부분의 공급업체는 항상 특정 URL(예: )을 허용할 수 있는 지침을 <https://support.google.com/chrome/a/answer/7532419> 제공합니다.

공격 시뮬레이션 교육에 사용되는 URL은 다음 목록에 설명되어 있습니다.

- <https://www.mcsharepoint.com>
- <https://www.attemplate.com>
- <https://www.doctricant.com>
- <https://www.mesharepoint.com>
- <https://www.officence.com>
- <https://www.officenced.com>
- <https://www.officences.com>
- <https://www.officentry.com>
- <https://www.officested.com>
- <https://www.prizegives.com>
- <https://www.prizemons.com>
- <https://www.prizewel.com>
- <https://www.prizewings.com>
- <https://www.shareholds.com>
- <https://www.sharepointen.com>
- <https://www.sharepointin.com>
- <https://www.sharepointle.com>
- <https://www.sharesbyte.com>
- <https://www.sharession.com>
- <https://www.sharestion.com>
- <https://www.templateau.com>
- <https://www.templatent.com>
- <https://www.templatern.com>
- <https://www.windocyte.com>

### <a name="create-a-simulation"></a>시뮬레이션 만들기

새 시뮬레이션을 만들고 보내는 방법에 대한 단계별 지침은 피싱 공격 [시뮬레이트를 참조하세요.](attack-simulation-training.md)

### <a name="create-a-payload"></a>페이로드 만들기

시뮬레이션 내에서 사용할 페이로드를 만드는 방법에 대한 단계별 지침은 공격 시뮬레이션 교육을 위한 사용자 지정 [페이로드 만들기를 참조하세요.](attack-simulation-training-payloads.md)

### <a name="gaining-insights"></a>인사이트 얻기

보고를 통해 인사이트를 얻는 방법에 대한 단계별 지침은 공격 시뮬레이션 교육을 통해 인사이트 [얻기를 참조하세요.](attack-simulation-training-insights.md)

> [!NOTE]
> 공격 시뮬레이터는 금고 Defender의 금고 링크를 사용하여 Office 365 링크 정책의 사용자 클릭 추적 안 하도록 설정되어 있는 경우에도 피싱 캠페인의  대상을 받는 사람에게 전송되는 페이로드 메시지의 URL에 대한 클릭 데이터를 금고 안전하게 추적합니다.
