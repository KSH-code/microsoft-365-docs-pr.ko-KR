---
title: 세 가지 파일 공유 보안 계층으로 Teams 구성
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
- m365solution-securecollab
- m365solution-scenario
ms.custom:
- Ent_Architecture
- seo-marvel-jun2020
ms.assetid: 1d51bd87-17bf-457c-b698-61821de3afa0
recommendations: false
description: 세 가지 보호 수준을 사용하여 보안을 강화하기 위해 Teams를 구성하는 방법에 대해 알아보고, 공동 작업을 쉽게 수행할 수 있습니다.
ms.openlocfilehash: 279e338af6db4d82291209deb66e1ea1eef74630
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60202336"
---
# <a name="configure-teams-with-three-tiers-of-protection"></a>세 가지 보호 계층으로 Teams 구성

이 시리즈의 문서에서는 간편한 공동 작업으로 보안의 균형을 조정하는 파일 보호를 위한 Microsoft Teams에서의 팀들과 그들과 연결된 SharePoint 사이트를 구성하기 위한 권장 사항을 제공합니다.

이 문서는 가장 공개적인 공유 정책을 사용하여 공개 팀을 시작하는 네 가지 다양한 구성을 정의합니다. 각각의 추가 구성은 보호 기능의 의미 있는 강화를 나타내고, 팀 내에 저장된 파일에 대한 액세스 및 공동 작업 기능은 관련 팀원의 집합으로 축소됩니다. 

이 문서의 구성은 데이터, ID 및 장치의 3계층 보호에 대한 Microsoft 권장 사항과 일치합니다.

- 초기 보호

- 중요한 보호

- 매우 중요한 보호

각 계층에 권장되는 계층과 기능에 대한 자세한 내용은 [엔터프라이즈 설계자를 위한 Microsoft 클라우드](./cloud-architecture-models.md)를 참조하세요.


## <a name="three-tiers-at-a-glance"></a>세 계층에 대한 간략한 정보

다음 표에서는 각 계층의 구성을 요약해서 보여줍니다. 이러한 구성을 시작하기 위한 권장 사항으로 사용하고, 조직의 요구 사항에 맞게 구성을 조정합니다. 모든 계층이 필요한 것은 아닙니다.

|-|기준(공개)|기준(비공개)|중요|매우 중요|
|:-----|:-----|:-----|:-----|:-----|
|비공개 또는 공개 팀|Public|개인|개인|개인|
|액세스 가능한 사용자|B2B 사용자를 포함한 조직의 모든 사용자|팀의 구성원만. 다른 사용자는 연결된 사이트에 대한 액세스를 요청할 수 있습니다.|팀의 구성원만.|팀의 구성원만.|
|비공개 채널|소유자와 구성원은 비공개 채널을 만들 수 있습니다.|소유자와 구성원은 비공개 채널을 만들 수 있습니다.|소유자만 비공개 채널을 만들 수 있습니다.|소유자만 비공개 채널을 만들 수 있습니다.|
|사이트 수준 게스트 액세스|**신규 및 기존 게스트**(기본값).|**신규 및 기존 게스트**(기본값).|**신규 및 기존 게스트** 또는 팀 요구에 따라 **조직의 사용자만**.|**신규 및 기존 게스트** 또는 팀 요구에 따라 **조직의 사용자만**.|
|사이트 공유 설정|**사이트 소유자 및 구성원, 편집 권한이 있는 사용자는 파일 및 폴더를 공유할 수 있지만 사이트는 오직 사이트 소유자만 공유할 수 있습니다**.|**사이트 소유자 및 구성원, 편집 권한이 있는 사용자는 파일 및 폴더를 공유할 수 있지만 사이트는 오직 사이트 소유자만 공유할 수 있습니다**.|**사이트 소유자 및 구성원, 편집 권한이 있는 사용자는 파일 및 폴더를 공유할 수 있지만 사이트는 오직 사이트 소유자만 공유할 수 있습니다**.|**오직 사이트 소유자만 파일, 폴더, 사이트를 공유할 수 있습니다**.<br>액세스 요청 **해제**.|
|사이트 수준 관리되지 않는 장치 액세스|**데스크톱 앱, 모바일 앱 그리고 웹에서의 모든 액세스**(기본값).|**데스크톱 앱, 모바일 앱 그리고 웹에서의 모든 액세스**(기본값).|**제한된 웹 전용 액세스 허용**.|**액세스 차단**.|
|기본 공유 링크 유형|**조직 내부 사용자만**|**조직 내부 사용자만**|**특정 사용자**|**기존 액세스를 지닌 사용자**|
|민감도 레이블|없음|없음|팀을 분류하고 게스트 공유 및 관리되지 않는 장치 액세스를 제어하는 데 사용되는 민감도 레이블입니다.|팀을 분류하고 게스트 공유 및 관리되지 않는 장치 액세스를 제어하는 데 사용되는 민감도 레이블입니다. 레이블을 파일에 암호화하는 데도 사용할 수 있습니다.|

매우 중요한 옵션의 변형으로, [보안 격리를 포함한 Teams](secure-teams-security-isolation.md)는 한 팀에 대해 고유한 민감도 레이블을 사용하여 추가 보안을 제공합니다. 이 레이블을 사용하여 파일을 암호화할 수 있으며, 해당 팀 구성원만 읽을 수 있게 됩니다.

초기 보호에는 공개 팀과 비공개 팀이 포함됩니다. 공개 팀은 조직의 모든 사용자가 검색하고 액세스할 수 있습니다. 개인 팀은 팀의 구성원만 검색하고 액세스할 수 있습니다. 이러한 두 가지 구성에서는 모두 권한 관리를 지원하기 위해 연결된 SharePoint 사이트의 공유를 팀 소유자로 제한합니다.

중요한 보호 및 매우 중요한 보호에 대한 Teams는 공유 및 연결된 사이트에 대한 액세스 요청이 제한되는 비공개 팀이며, 민감도 레이블을 사용하여 게스트 공유, 장치 액세스 및 콘텐츠 암호화에 대한 정책을 설정합니다.

## <a name="sensitivity-labels"></a>민감도 레이블

중요한 계층 및 매우 중요한 계층에서는 민감도 레이블을 사용하여 팀과 파일을 보호합니다. 이러한 계층을 구현하려면 [Microsoft Teams, Office 365 그룹 및 SharePoint 사이트에서 민감도 레이블 사용하여 콘텐츠 보호하기](../compliance/sensitivity-labels-teams-groups-sites.md)를 활성화합니다.

기준 계층에는 민감도 레이블이 필요하지 않지만 "일반" 레이블을 만든 다음 모든 팀에 레이블을 지정하는 것이 좋습니다. 이렇게 하면 팀을 만들 때 해당 사용자가 민감도를 쉽게 확인할 수 있습니다. 중요한 또는 매우 중요한 계층을 배포하려는 경우 기준 팀과 중요하지 않은 파일에 사용할 수 있는 "일반" 레이블을 만드는 것이 좋습니다.

민감도 레이블을 처음 사용하는 경우 [민감도 레이블 시작하기](../compliance/get-started-with-sensitivity-labels.md)를 읽고 시작하는 것이 좋습니다. 

조직에서 민감도 레이블이 이미 배포된 경우 중요한 및 매우 중요한 계층에서 사용되는 레이블이 전반적인 레이블 전략에 어떻게 적용되는지 고려합니다. 

## <a name="sharing-the-sharepoint-site"></a>SharePoint 사이트 공유

각 팀에는 문서가 저장되는 연결된 SharePoint 사이트가 있습니다. (이것은 팀 채널의 **파일** 탭입니다.) SharePoint 사이트에는 고유한 사용 권한 관리가 유지되지만 팀 권한에 연결됩니다. 팀 소유자는 사이트 소유자로 포함되고 팀 구성원은 연결된 사이트에서 사이트 구성원으로 포함됩니다.

결과로 제공되는 권한을 사용하여 다음을 수행할 수 있습니다.

- 팀 소유자가 사이트를 관리하고 사이트 콘텐츠를 전체적으로 제어할 수 있습니다.
- 팀 구성원이 사이트에서 파일을 만들고 편집할 수 있습니다. 

기본적으로 팀 소유자와 구성원은 팀 외부의 사용자를 실제로 팀에 추가하지 않고도 이들과 사이트를 공유할 수 있습니다. 그러나 이는 사용자 관리를 복잡하게 만들고 팀 구성원이 아닌 사용자가 팀 소유자의 허락없이 팀 파일에 액세스할 수 있는 상황이 발생할 수 있으므로 권장하지 않습니다. 이를 방지하려면 기준 보호 수준에서 시작하여 소유자만 사이트를 직접 공유할 수 있도록 하는 것이 좋습니다.

팀에는 읽기 전용 권한 옵션이 없지만 SharePoint 사이트에는 해당 옵션이 있습니다. 팀 파일을 볼 수 있고 편집할 수는 없어야 하는 파트너 그룹의 이해 관계자가 있는 경우 읽기 권한을 사용하여 SharePoint 사이트에 직접 추가하는 것이 좋습니다.

## <a name="sharing-files-and-folders"></a>파일 및 폴더 공유

기본적으로 팀 소유자와 팀 구성원 모두 팀 외부의 사용자와 파일 및 폴더를 공유할 수 있습니다. 게스트 공유를 허용한 경우 조직 외부의 사용자가 포함될 수 있습니다. 세 계층 모두 실수로 과도하게 공유하는 것을 방지할 수 있도록 기본 공유 링크 유형을 업데이트합니다. 매우 중요한 계층에서는 이러한 공유를 팀 소유자로만 제한합니다.

## <a name="guest-sharing"></a>게스트 공유

조직 외부의 사용자와 공동 작업을 해야 하는 경우 최상의 공유 및 관리 환경을 위해 [Azure AD B2B와 SharePoint 및 OneDrive 통합](/sharepoint/sharepoint-azureb2b-integration-preview)을 구성하는 것이 좋습니다.

Teams 게스트 공유는 기본적으로 켜져 있지만 필요한 경우 민감도 레이블을 사용하여 민감하고 매우 민감한 계층에서 끌 수 있습니다.

매우 중요한 계층에서는 적용되는 파일을 암호화하도록 민감도 레이블을 구성합니다. 게스트에게 이러한 파일에 대한 액세스 권한이 필요한 경우 레이블을 만들 때 해당 게스트에게 권한을 부여해야 합니다.

조직 외부의 사용자와 공동 작업을 수행해야 하는 경우 기준 계층 및 중요한 계층 또는 매우 중요한 계층에 대해 게스트 공유를 유지하는 것이 좋습니다. Microsoft 365의 게스트 공유 기능은 파일을 전자 메일 메시지의 첨부 파일로 보내는 것보다 훨씬 안전하고 관리 가능한 공유 환경을 제공합니다. 또한 사용자가 관리되지 않는 소비자 제품을 사용하여 합법적인 외부 공동 작업자와 공유하는 섀도 IT의 위험을 줄입니다.

조직에 안전하고 생산적인 게스트 공유 환경을 만들려면 다음 참조를 확인하세요.

- [인증되지 않은 사용자와 파일 및 폴더를 공유하는 최우수 사례](best-practices-anonymous-sharing.md)
- [파일을 조직 외부의 사람들과 공유할 때 실수로 발생하는 정보 노출 제한하기](share-limit-accidental-exposure.md)
- [보안 게스트 공유 환경 만들기](create-secure-guest-sharing-environment.md)

## <a name="access-from-unmanaged-devices"></a>관리되지 않는 장치에서 액세스

중요한 계층 및 매우 중요한 계층의 경우 민감도 레이블이 포함된 SharePoint 콘텐츠에 대한 액세스를 제한합니다. Azure AD 조건부 액세스는 위치, 위험, 장치 호환성 및 기타 요인에 따른 제한을 비롯하여 사용자가 Microsoft 365에 액세스하는 방법을 결정하는 데 사용할 수 있는 다양한 옵션을 제공합니다. [조건부 액세스란 무엇인가요?](/azure/active-directory/conditional-access/overview)를 읽는 것을 권장합니다. 또한 조직에 적합한 추가 정책을 고려하세요.

게스트에게는 조직에서 관리하는 장치가없는 경우가 많습니다. 계층에서 게스트를 허용하는 경우 게스트가 팀 및 사이트에 액세스하는 데 사용할 디바이스 유형을 고려하고 그에 따라 관리되지 않는 디바이스 정책을 설정합니다.

### <a name="control-device-access-across-microsoft-365"></a>Microsoft 365 장치 액세스 제어

민감도 레이블의 관리되지 않는 디바이스 설정은 SharePoint 액세스에만 영향을 줍니다. SharePoint를 넘어 관리되지 않는 장치에 대한 제어를 확장하려면 대신 [조직의 모든 앱 및 서비스에 대한 Azure Active Directory 조건부 액세스 정책을 만들 수](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) 있습니다. 이 정책을 [Microsoft 365 서비스](/azure/active-directory/conditional-access/concept-conditional-access-cloud-apps#office-365)에 맞게 구성하려면 **클라우드 앱 또는 작업** 아래에서 **Office 365** 클라우드 앱을 선택하세요.

![Microsoft Azure Active Directory 조건부 액세스 정책의 Office 365 클라우드 앱 스크린샷](/sharepoint/sharepointonline/media/azure-ca-office365-policy.png)

모든 Microsoft 365 서비스에 영향을 미치는 정책을 사용하면 사용자에게 더 나은 보안과 더 나은 환경을 제공할 수 있습니다. 예를 들어 SharePoint에서만 관리되지 않는 장치에 대한 액세스를 차단하면 사용자가 관리되지 않는 장치가 있는 팀의 채팅에 액세스할 수 있지만 **파일** 탭에 액세스하려고 하면 액세스 권한이 손실됩니다. Office 365 클라우드 앱을 사용하면 [서비스 종속성](/azure/active-directory/conditional-access/service-dependencies)에 대한 문제를 방지할 수 있습니다.

## <a name="next-step"></a>다음 단계

[기준 수준의 보호 구성](configure-teams-baseline-protection.md)으로 시작합니다. 필요한 경우 기준 보호 외에 [중요한 보호](configure-teams-sensitive-protection.md) 및 [매우 중요한 보호](configure-teams-highly-sensitive-protection.md)를 추가할 수 있습니다.

## <a name="see-also"></a>기타 참고 항목

[Microsoft Teams의 보안 및 규정 준수](/microsoftteams/security-compliance-overview)

[보안 및 준수 센터의 경고 정책](../compliance/alert-policies.md)
