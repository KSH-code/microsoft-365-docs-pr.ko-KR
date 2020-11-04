---
title: Microsoft 365를 사용하여 안전한 공동 작업 설정
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-securecollab
- m365solution-overview
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
description: 팀에서 보안 콘텐츠 공동 작업을 설정 하 여 해당 민감도를 기반으로 데이터를 보호 하는 방법을 알아봅니다.
ms.openlocfilehash: 310605d0db84e33be1d5fdc925fadcfcdf9dddaf
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906802"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a>Microsoft 365를 사용하여 안전한 공동 작업 설정

조직의 성공적인 공유를 방지 하면서 적절 한 사람들과 쉽게 정보를 공유할 수 있습니다. 여기에는 액세스 권한이 있는 사람만 중요 한 데이터를 안전 하 게 공유할 수 있는 권한이 포함 됩니다. 프로젝트에 따라 중요 한 데이터를 조직 외부의 사용자와 공유 하는 것이 여기에 포함 될 수 있습니다.

이 공동 작업 솔루션 지침에는 다음과 같은 두 가지 구성 요소가 포함 됩니다.
- 각 프로젝트에 적절 한 수준의 보호를 사용 하 여 Microsoft 팀 배포
- 각 프로젝트에 대해 적절 한 보안 설정을 사용 하 여 외부 공유 구성

![적절 한 보호를 사용 하 여 팀 배포 및 적절 한 보안 설정을 사용 하 여 외부 공유 구성](..\media\solutions-architecture-center\secure-collaboration-overview.png)

다양 하 고 사용 하기 쉬운 콘텐츠 공동 작업 도구를 사용할 수 없는 경우 사용자는 문서를 이메일로 보내 자주 공동 작업을 수행 하 게 됩니다. 이는 공동 작업을 위한 지루한 및 오류가 발생 하기 쉬운 방법으로, 부적절 한 정보 공유 위험을 높일 수 있습니다. 사용자가 너무 어려운 공유 정보를 찾는 경우에는 해당 정보가 관리 되지 않는 소비자 제품을 사용 하 여 되돌릴 수 있습니다. 이 경우 훨씬 더 많은 위험을 초래할 수 있습니다.

Microsoft 365에서는 다음과 같은 다양 한 구성을 사용 하 여 팀을 배포할 수 있습니다.

- 지적 재산 보호
- 손쉬운 공동 작업 사용
- 보안 및 편리성 간의 균형을 조정 하 여 사용자 만족도를 높여 섀도 IT의 위험을 줄입니다.

대부분의 조직에는 정보가 부적절 하 게 공유 되는 경우 다양 한 수준의 민감도와 다양 한 비즈니스 영향을 갖는 여러 정보가 있습니다. 지정 된 정보 부분의 민감도에 따라 다음을 사용할 수 있습니다.

- 모든 사용자 (인증 되지 않음)
- 조직 내부의 사용자
- 조직 내부의 특정 사용자
- 조직 내부 및 외부의 특정 사용자

마케팅 브로셔와 같은 정보는 조직 외부에서 광범위 하 게 공유할 수 있습니다. Cafeteria 메뉴와 같은 정보는 외부 공유를 위한 것이 아니라 외부적으로 공유 하는 경우에는 비즈니스에 영향을 주지 않습니다. 이러한 유형의 정보는 보호를 거의 또는 전혀 수행 하지 않아도 됩니다.

이러한 동일한 마케팅 브로슈어를 개발 중에는 조직 내 에서만 공유할 수 있습니다. 이 경우 팀의 기본 공유 설정이 충분할 수 있습니다.

개발 중인 새 제품에 대 한 정보는 조직 내 에서도 중요 한 것으로 간주 될 수 있습니다. 이 경우에는 보다 높은 수준의 보호가 적합할 수 있습니다. 예를 들어 특정 팀의 구성원에 게이 정보에 대 한 액세스를 제한할 수 있습니다. 프로젝트에 따라 공급 업체 또는 파트너 조직과 같이 조직 외부의 사용자와 공동 작업을 해야 할 수 있습니다.

조직의 성공 또는 엄격한 보안 또는 준수 요구 사항에 중요 한 정보를 포함 하는 경우 더 많은 보호 수준도 필요할 수 있습니다.

![낮음 (브로슈어 출시)에서 높음 (중요 한 비즈니스 데이터)까지 위험 확장](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

위에 언급 된 모든 시나리오에 대해 Microsoft 팀의 팀을 사용 하 여 정보를 저장, 공유 및 공동 작업할 수 있습니다. 

보안 collabration를 구성 하기 위해 이러한 Microsoft 365 기능과 기능을 사용 합니다.

| 제품 또는 구성 요소 | 기능 또는 특징 | 라이선싱 |
|:-------|:-----|:-------|
| Microsoft Defender for Office 365 | SPO, OneDrive 및 팀에 대 한 안전한 첨부 파일 안전한 문서 팀에 대 한 안전한 링크    | Microsoft 365 E1, E3 및 E5 |
| SharePoint    | 사이트 및 파일 공유 정책, 사이트 공유 권한, 공유 링크, 액세스 요청, 사이트 게스트 공유 설정 | Microsoft 365 E1, E3 및 E5 |
| Microsoft Teams   | 게스트 액세스, 개인 팀, 개인 채널 | Microsoft 365 E1, E3 및 E5 |
| Microsoft 365 규정 준수  | 민감도 레이블    | Microsoft 365 E3 및 E5 |

### <a name="using-teams-for-all-kinds-of-data"></a>모든 종류의 데이터에 대 한 팀 사용

다른 sensitivities 정보에 대 한 액세스를 관리 하기 위해 [팀에서 세 가지 다른 수준의 보호](configure-teams-three-tiers-protection.md)를 개발 했습니다. 이러한 계층을 사용자 지정 하 여 요구 사항 또는 비즈니스에 보다 적합 한 주소를 지정할 수 있습니다. 

![Teams 논리 아키텍처 포스터의 축소판 그림 이미지](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


이러한 계층- *초기 계획* , *중요* 및 *높은 수준의 중요* -다음 표와 같이 과잉 공유 및 잠재적인 정보 누출을 방지 하는 보호 기능을 단계적으로 향상 시킵니다.

||**기본 계층**|**중요 계층**|**높은 중요 계층**|
|:--|:-----------|:------------|:-------------------|
|공용 또는 비공개 팀|일|개인|개인|
|인증되지 않은 공유|차단됨|차단됨|차단됨|
|파일 공유|허용됨|허용됨|팀 소유자만 공유할 수 있습니다.|
|팀 구성원|모든 사용자가 공용 팀에 참가할 수 있습니다.<br>비공개 팀에 참가 하는 데 필요한 팀 소유자 승인|참가 하는 데 필요한 팀 소유자 승인입니다.|참가 하는 데 필요한 팀 소유자 승인입니다.|
|문서 암호화|||민감도 레이블 사용 가능|
|게스트 공유|허용됨|허용 하거나 차단할 수 있습니다.|허용 하거나 차단할 수 있습니다.|
|관리 되지 않는 장치|제한 없음|웹 전용 액세스|차단됨|

이러한 계층 구성에는 다음이 포함 됩니다.

- 게스트 액세스 및 개인 채널에 대 한 팀의 설정 구성
- 내부 및 게스트 공유, 액세스 요청 및 공유 링크에 대 한 팀의 연결 된 SharePoint 사이트의 설정 구성
- *중요* 및 *중요 한* 계층의 경우 팀을 분류 하기 위한 민감도 레이블을 구성 하 고 관리 되지 않는 장치에서 게스트 공유 및 액세스 제어
- 중요도가 *높은* 계층의 경우 적용 되는 문서를 암호화 하는 민감도 레이블을 구성 합니다.

기본 계층부터 시작한 다음 필요에 따라 *중요* 하 고 *중요* 한 계층을 사용 하는 팀을 추가 하 여 조직의 정보를 보호 하는 데 도움을 주는 방법을 설명 합니다. 시작 하려면 다음 리소스를 참조 하세요.

- [기본 보호 기능으로 팀 구성](configure-teams-baseline-protection.md)
- [중요한 데이터를 보호하는 팀 구성하기](configure-teams-sensitive-protection.md)
- [매우 중요한 데이터를 보호하는 팀 구성하기](configure-teams-highly-sensitive-protection.md)

조직 내 에서도 공유 기능을 추가로 보호 해야 하는 중요 한 프로젝트가 있는 경우 해당 민감도 레이블을 사용 하 여 팀 구성원만 읽을 수 있도록 파일을 암호화 하는 팀을 구성할 수 있습니다. 자세한 내용은 [보안 격리를 사용 하 여 팀 구성을](secure-teams-security-isolation.md) 참조 하세요.

### <a name="sharing-with-people-outside-your-organization"></a>조직 외부의 사용자와 공유

[조직 외부의 사용자와의 민감도 정보를 공유](collaborate-with-people-outside-your-organization.md)해야 할 수 있습니다. 이는 단일 문서를 공유 하 여 대규모 파트너 조직이 나 전 세계의 freelancers 주요 프로젝트에서 공동 작업을 수행할 수 있는 범위입니다. Microsoft 365에서이 범위 외부 공유는 중요 한 정보를 보호 하는 데 적합 한 적절 한 보호책을 사용 하 여 쉽게 수행할 수 있습니다.

이러한 리소스를 사용 하면 조직 외부의 사용자와 공동으로 작업할 수 있도록 환경을 설정 하는 작업을 시작 하는 데 도움이 됩니다.

- 개별 폴더 파일을 공유할 [문서를 공동 작업](collaborate-on-documents.md) 합니다.
- SharePoint 사이트에서 게스트와 공동 작업 하기 위해 [사이트에서 협력](collaborate-in-site.md) 합니다.
- 팀 [과 공동 작업](collaborate-as-team.md) 을 수행 하는 팀의 게스트

공유 되는 정보의 민감도에 따라, 과잉 공유를 방지 하는 보호 기능을 추가할 수 있습니다. 이러한 리소스는 조직에 필요한 보호를 설정 하는 데 도움이 됩니다.

- [인증되지 않은 사용자와 파일 및 폴더를 공유하는 최우수 사례](best-practices-anonymous-sharing.md)
- [파일을 조직 외부의 사람들과 공유할 때 실수로 발생하는 정보 노출 제한하기](share-limit-accidental-exposure.md)
- [보안 게스트 공유 환경 만들기](create-secure-guest-sharing-environment.md)

파트너 조직이 포함 된 주요 프로젝트인 경우 Azure 권한 관리를 사용 하 여 프로젝트에 대해 설정한 팀의 해당 조직에서 게스트를 관리할 수 있습니다. 자세한 내용은 [관리 되는 게스트를 사용 하 여 B2B 엑스트라넷 만들기](b2b-extranet.md) 를 참조 하세요.

## <a name="deploy-the-secure-collaboration-solution"></a>보안 공동 작업 솔루션 배포

이 솔루션을 배포할 준비가 되 면 다음 단계를 계속 진행 합니다.
1. 세 가지 [다른 유형의 팀 보호](configure-teams-three-tiers-protection.md)를 구성 합니다.
2. [조직 외부의 사용자와의 모든 민감도 정보 공유](collaborate-with-people-outside-your-organization.md)에 대 한 설정을 구성 합니다.

## <a name="see-also"></a>참고 항목

[Microsoft 365 보안 설명서](https://docs.microsoft.com/microsoft-365/security)

[Microsoft 365 규정 준수 설명서](https://docs.microsoft.com/microsoft-365/compliance)

[Microsoft Teams에 오신 것을 환영합니다.](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
