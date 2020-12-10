---
title: Microsoft 365를 사용하여 안전한 공동 작업 설정
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: Teams에서 보안 콘텐츠 공동 작업을 설정하여 민감도에 따라 데이터를 보호하는 방법을 알아보겠습니다.
ms.openlocfilehash: f65657125fef8b8cf7e4e229d70d8fe211153392
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613587"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a>Microsoft 365를 사용하여 안전한 공동 작업 설정

조직에서 과도하게 공유하는 것을 방지하면서 올바른 사용자와 정보를 쉽게 공유할 수 있는 것이 조직의 성공에 핵심입니다. 여기에는 중요한 데이터를 액세스 권한이 있는 사용자와만 안전하게 공유할 수 있습니다. 프로젝트에 따라 조직 외부의 사용자와 중요한 데이터를 공유하는 것이 포함됩니다.

이 공동 작업 솔루션 지침에는 다음 두 가지 구성 요소가 포함되어 있습니다.
- 각 프로젝트에 대한 올바른 보호 수준을 통해 Microsoft Teams 배포
- 각 프로젝트에 대해 적절한 보안 설정을 사용하여 외부 공유 구성

![적절한 보호를 사용하여 Teams 배포 및 적절한 보안 설정으로 외부 공유 구성](..\media\solutions-architecture-center\secure-collaboration-overview.png)

다용도 및 사용하기 쉬운 콘텐츠 공동 작업 도구를 사용할 수 없는 경우 사용자는 문서를 전자 메일로 보내 공동 작업을 하는 경우가 종종 있습니다. 이는 공동 작업의 지우고 오류가 발생할 수 있는 방법으로, 부적절한 정보 공유의 위험을 증가할 수 있습니다. 공유 정보가 너무 어렵다는 것을 발견하면 IT에서 관리하지 않는 소비자 제품을 다시 사용할 수 있습니다. 이는 훨씬 더 큰 위험을 내포할 수 있습니다.

Microsoft 365를 사용하면 다음을 도와주는 다양한 구성으로 Teams를 배포할 수 있습니다.

- 지적 재산 보호
- 간편한 공동 작업 사용
- 보안과 사용성 간의 균형을 유지하여 사용자 만족도를 향상하고 섀도 IT의 위험을 줄입니다.

대부분의 조직에서는 정보가 부적절하게 공유되는 경우 민감도 및 비즈니스 영향 정도가 다양한 다양한 정보를 제공합니다. 특정 정보의 민감도에 따라 다음과의 공유를 허용할 수 있습니다.

- 모든 사람(비인식)
- 조직 내부 사용자
- 조직 내부의 특정 사용자
- 조직 내부 및 외부의 특정 사용자

마케팅 브로셔와 같은 정보는 조직 외부에서 광범위하게 공유하기 위한 것입니다. 카페테리아 메뉴와 같은 정보는 외부 공유를 위한 것이 아니라 외부에서 공유된 경우 비즈니스에 영향을 줄 수 없습니다. 이러한 유형의 정보는 보호가 거의 또는 필요하지 않습니다.

개발 중에는 조직 내에서만 동일한 마케팅 브로셔를 공유할 수 있습니다. 이 경우 Teams의 기본 공유 설정으로 충분할 수 있습니다.

개발 중인 새 제품에 대한 정보는 조직 내에서도 중요한 것으로 간주될 수 있습니다. 이 경우 더 높은 수준의 보호가 적절할 수 있습니다. 예를 들어 이 정보에 대한 액세스를 특정 팀의 구성원으로 제한할 수 있습니다. 프로젝트에 따라 공급업체 또는 파트너 조직과 같은 조직 외부의 사용자와 공동 작업을 해야 할 수 있습니다.

조직의 성공에 중요하거나 엄격한 보안 또는 규정 준수 요구 사항이 있는 정보는 훨씬 더 높은 수준의 보호가 필요할 수 있습니다.

![위험 수준이 낮음(릴리스된 브로셔)에서 높은(중요한 비즈니스 데이터)로 확장](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

위에서 설명한 모든 시나리오에 대해 Microsoft Teams의 팀을 사용하여 정보를 저장, 공유 및 공동 작업할 수 있습니다. 

보안 공동 작업을 구성하기 위해 이러한 Microsoft 365 기능 및 기능을 사용하게 됩니다.

| 제품 또는 구성 요소 | 기능 또는 특징 | 라이선싱 |
|:-------|:-----|:-------|
| Office 365용 Microsoft Defender | SPO, OneDrive 및 Teams에 대한 안전한 첨부 파일 안전한 문서 Teams에 대한 안전한 링크    | Microsoft 365 E1, E3 및 E5 |
| SharePoint    | 사이트 및 파일 공유 정책, 사이트 공유 권한, 공유 링크, 액세스 요청, 사이트 게스트 공유 설정 | Microsoft 365 E1, E3 및 E5 |
| Microsoft Teams   | 게스트 액세스, 비공개 팀, 비공개 채널 | Microsoft 365 E1, E3 및 E5 |
| Microsoft 365 규정 준수  | 민감도 레이블    | Microsoft 365 E3 및 E5 |

### <a name="using-teams-for-all-kinds-of-data"></a>모든 종류의 데이터에 Teams 사용

민감도가 다른 정보에 대한 액세스를 관리하기 위해 Teams에 대한 세 가지 보호 [계층을 개발했습니다.](configure-teams-three-tiers-protection.md) 이러한 계층을 사용자 지정하여 요구 또는 비즈니스를 보다 잘 해결할 수 있습니다. 

![Teams 논리 아키텍처 포스터의 축소판 그림 이미지](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


이러한 계층(기준, 중요 및  중요도)은 다음 표와 같이 과도하게 공유 및 잠재적인 정보 누출을 방지하는 데 도움이 되는 보호 기능을 점진적으로 늘려나가고 있습니다. 

|-|**기준 계층**|**중요 계층**|**높은 중요 계층**|
|:--|:-----------|:------------|:-------------------|
|공개 또는 비공개 팀|둘 중 하나|개인|개인|
|인증되지 않은 공유|차단됨|차단됨|차단됨|
|파일 공유|허용됨|허용됨|팀 소유자만 공유할 수 있습니다.|
|팀 구성원|누구나 공개 팀에 참가할 수 있습니다.<br>비공개 팀에 참가하는 데 팀 소유자 승인이 필요합니다.|참가에 팀 소유자 승인이 필요합니다.|참가에 팀 소유자 승인이 필요합니다.|
|문서 암호화|||민감도 레이블과 함께 사용 가능|
|게스트 공유|허용됨|허용 또는 차단할 수 있습니다.|허용 또는 차단할 수 있습니다.|
|관리되지 않는 장치|제한 없음|웹 전용 액세스|차단됨|

이러한 계층을 구성하는 과정에는 다음이 수반됩니다.

- 게스트 액세스 및 비공개 채널에 대한 Teams의 설정 구성
- 팀의 연결된 SharePoint 사이트에서 내부 및 게스트 공유, 액세스 요청 및 공유 링크를 위한 설정 구성
- 중요하고  매우 *중요한* 계층의 경우 팀을 분류하고, 관리되지 않는 장치에서 게스트 공유 및 액세스를 제어하기 위해 민감도 레이블을 구성합니다.
- 매우 *중요한 계층의* 경우 민감도 레이블을 구성하여 해당 계층이 적용되는 문서를 암호화합니다.

기준 계층으로 시작한 다음, 필요한 경우  중요하고 중요한 계층을 사용하는 팀을 추가하여 조직의 정보를 보호합니다.  시작을 위해 다음 리소스를 참조합니다.

- [기본 보호 기능으로 팀 구성](configure-teams-baseline-protection.md)
- [중요한 데이터를 보호하는 팀 구성하기](configure-teams-sensitive-protection.md)
- [매우 중요한 데이터를 보호하는 팀 구성하기](configure-teams-highly-sensitive-protection.md)

조직 내에서도 공유로부터 추가 보호가 필요한 매우 중요한 프로젝트가 있는 경우 팀 구성원만 읽을 수 있도록 자체 민감도 레이블을 사용하는 팀을 구성하여 파일을 암호화할 수 있습니다. 자세한 [내용은 보안이 있는](secure-teams-security-isolation.md) 팀 구성을 참조합니다.

### <a name="sharing-with-people-outside-your-organization"></a>조직 외부의 사용자와 공유

조직 외부의 사용자와 민감도 정보를 [공유해야 할 수 있습니다.](collaborate-with-people-outside-your-organization.md) 단일 사용자와 단일 문서를 공유하는 것부터 대규모 파트너 조직 또는 전 세계의 프리랜서와 주요 프로젝트 공동 작업까지 다양할 수 있습니다. Microsoft 365에서 이 범위의 외부 공유는 중요한 정보를 보호하는 데 도움이 되는 적절한 세이프가드를 사용하여 쉽게 완료할 수 있습니다.

이러한 리소스는 조직 외부의 사용자와 공동 작업을 위한 환경을 설정하는 데 도움이 됩니다.

- [개별 폴더 파일을 공유하기](collaborate-on-documents.md) 위해 문서에 대해 공동 작업을 합니다.
- [](collaborate-in-site.md) SharePoint 사이트에서 게스트와 공동 작업을 할 수 있는 사이트에서 공동 작업을 합니다.
- [팀의](collaborate-as-team.md) 게스트와 공동 작업을 위한 팀으로 공동 작업을 합니다.

공유되는 정보의 민감도에 따라 과도하게 공유되지 않도록 보호 장치를 추가할 수 있습니다. 이러한 리소스는 조직에 필요한 보호를 설정하는 데 도움이 됩니다.

- [인증되지 않은 사용자와 파일 및 폴더를 공유하는 최우수 사례](best-practices-anonymous-sharing.md)
- [파일을 조직 외부의 사람들과 공유할 때 실수로 발생하는 정보 노출 제한하기](share-limit-accidental-exposure.md)
- [보안 게스트 공유 환경 만들기](create-secure-guest-sharing-environment.md)

파트너 조직이 있는 주요 프로젝트가 있는 경우 Azure 권한 관리 기능을 사용하여 해당 조직의 게스트를 프로젝트에 대해 설정한 팀에서 관리할 수 있습니다. 자세한 [내용은 관리되는 게스트가 있는 B2B 엑스트라넷](b2b-extranet.md) 만들기를 참조합니다.

## <a name="deploy-the-secure-collaboration-solution"></a>보안 공동 작업 솔루션 배포

이 솔루션을 배포할 준비가 되면 다음 단계를 계속 진행합니다.
1. Teams에 대한 세 가지 보호 [계층을 구성합니다.](configure-teams-three-tiers-protection.md)
2. 조직 외부의 사용자와 민감도 정보를 [공유하기 위한 설정을 구성합니다.](collaborate-with-people-outside-your-organization.md)

## <a name="see-also"></a>참고 항목

[Microsoft 365 보안 설명서](https://docs.microsoft.com/microsoft-365/security)

[Microsoft 365 규정 준수 설명서](https://docs.microsoft.com/microsoft-365/compliance)

[Microsoft Teams에 오신 것을 환영합니다.](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
