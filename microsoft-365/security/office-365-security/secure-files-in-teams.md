---
title: Microsoft Teams에서의 파일 보호
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom:
- Ent_Architecture
ms.assetid: 1d51bd87-17bf-457c-b698-61821de3afa0
description: '요약: Microsoft Teams에서의 파일을 보호하기 위한 구성 권장 사항입니다.'
ms.openlocfilehash: 1b4d5205836337b02c831341d5de65a87dba6fc5
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925837"
---
# <a name="secure-files-in-microsoft-teams"></a>Microsoft Teams에서의 파일 보호

이 문서에서는 간편한 공동 작업으로 보안의 균형을 조정하는 파일 보호를 위한 Microsoft Teams에서의 팀들과 그들의 기본 SharePoint 사이트를 구성하기 위한 권장 사항을 제공합니다. 이 문서는 가장 공개적인 공유 정책을 사용하여 조직 내에서 공용 사이트를 시작하는 네 가지 다양한 구성을 정의합니다. 각각의 추가 구성은 보호 기능의 의미 있는 강화를 나타내지만, Teams 내에 저장된 파일에 대한 액세스 및 공동 작업 기능은 관련 팀원의 집합으로 축소됩니다. 이러한 권장 사항에 기반하여 시작하고 조직의 요구 사항에 맞게 해당 구성을 조정합니다. 
  
이 문서의 구성은 데이터, ID 및 장치의 3계층 보호에 대한 Microsoft 권장 사항과 일치합니다.
  
- 초기 보호
    
- 중요 보호
    
- 극비 보호
    
이러한 계층 및 각 계층에 권장되는 기능에 대한 자세한 내용은 다음 리소스를 참조하세요. 
  
- [Office 365용 ID 및 장치 보호](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#BKMK_O365IDP)
    
- [Office 365의 파일 보호 솔루션](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#BKMK_O365fileprotect)
    
## <a name="capability-overview"></a>기능 개요

보안 팀에 대한 권장 사항은 다양한 Microsoft 365 기능을 활용합니다. 다음의 그림은 권장되는 구성을 보여줍니다.

![팀에 권장되는 구성](../media/secure-team-configurations.png)

그림에서 보듯이 다음과 같이 설명할 수 있습니다.
  
- 기준 보호에는 공개 팀과 비공개 팀이 모두 포함됩니다. 공개 팀은 조직의 모든 사용자가 검색하고 액세스할 수 있습니다. 개인 팀은 팀의 구성원만 검색하고 액세스할 수 있습니다. 이러한 두 가지 구성 모두 파일이 팀 그룹 외부에 저장되는 기본 SharePoint 사이트의 공유를 가능하게 해줍니다.
 
- 중요하고 극비의 보호를 위한 팀은 기본 사이트에 대한 액세스의 공유 및 요청이 제한되는 비공개 팀입니다.

    
- [보존 레이블](../../compliance/labels.md)은 기본 SharePoint 사이트 내의 파일을 분류하는 방법을 제시합니다. 각 기본 SharePoint 사이트는 기본 보존 레이블을 통해 문서 라이브러리의 파일에 자동으로 레이블을 지정하도록 구성됩니다. 4가지 팀의 구성에 해당하는 이 예제의 레이블은 내부 공개, 비공개, 중요 그리고 극비입니다. 사용자는 개별 파일에 대한 레이블을 변경할 수 있지만 이 구성은 모든 파일에서 기본 레이블을 받도록 합니다.
    
- 사용자가 조직 외부로 이러한 종류의 파일을 보내려고 할 때 경고하거나 방지하기 위해 중요 및 극비 보존 레이블에 대한 [데이터 손실 방지](../../compliance/data-loss-prevention-policies.md)(DLP) 정책이 구성됩니다.
    
- 시나리오에 필요한 경우 [민감도 레이블](../../compliance/sensitivity-labels.md)을 사용하여 기밀성이 높은 파일을 암호화 및 사용 권한으로 보호할 수 있습니다. Azure Information Protection 고객의 경우 Microsoft 365 준수 센터에서 Azure Information Protection 레이블을 사용할 수 있으며 추가 또는 고급 구성을 수행하기로 선택한 경우 레이블이 Azure 포털과 동기화됩니다. Azure Information Protection 레이블과 Office 365 민감도 레이블은 서로 완벽하게 호환됩니다. 예를 들어, Azure Information Protection으로 분류된 콘텐츠가 있는 경우 콘텐츠를 재 분류하거나 레이블을 다시 지정할 필요가 없습니다.  모든 고객이 이러한 수준의 보호를 필요로 하지는 않습니다. 
    
## <a name="organization-wide-settings-for-sharepoint-and-onedrive"></a>SharePoint 및 OneDrive에 대한 조직 전체의 설정

SharePoint 및 OneDrive에는 모든 사이트 및 사용자에게 영향을 주는 조직 전체의 설정이 포함됩니다. 또한 이러한 설정 중 일부는 사이트 수준에서 더 제한적으로 조정할 수 있지만 해당 제한을 완화할 수는 없습니다. 이 섹션에서는 보안 및 공동 작업에 영향을 주는 테넌트 수준 설정에 대해 설명합니다. 
  
### <a name="sharing"></a>공유

이 솔루션의 경우 다음과 같은 조직 전체의 설정을 사용하는 것이 좋습니다.
  
- 익명 공유를 포함하여 모든 계정 유형과 공유할 수 있도록 허용하는 기본 공유 정책을 유지합니다.
    
- 필요한 경우 익명 연결이 만료되도록 설정합니다.
    
- 공유할 기본 연결 종류를 내부로 변경합니다. 이렇게 하면 실수로 데이터를 조직 외부로 누출하지 않도록 방지할 수 있습니다.
    
외부 공유를 허용하는 것이 반직관적일 수 있지만, 이 방법은 전자 메일로의 파일의 전송에 비해 파일 공유에 대한 더욱 상세한 컨트롤을 제공합니다. SharePoint와 Outlook은 함께 작동하여 파일에 대한 안전한 공동 작업을 제공합니다. 
  
- 기본적으로 Outlook은 전자 메일로 파일을 보내는 대신 파일에 대한 링크를 공유합니다. 
    
- SharePoint와 OneDrive를 사용하면 조직 내부와 외부 모두의 참가자와 파일로의 링크를 쉽게 공유할 수 있습니다.
    
또한 외부 공유를 관리하는 데 도움이 되는 제어가 있습니다. 예를 들어, 다음을 수행할 수 있습니다.
  
- 익명 게스트 링크를 사용하지 않도록 설정합니다.
    
- 사이트에 대한 사용자 액세스를 취소합니다.
    
- 특정 사이트 또는 문서에 대한 액세스 권한이 있는 사용자인지 확인합니다.
    
- 익명 공유 링크 만료를 설정합니다(테넌트 설정).
    
- 조직 외부에서 공유할 수 있는 사용자를 제한합니다(테넌트 설정).
    
### <a name="use-external-sharing-together-with-data-loss-prevention-dlp"></a>DLP(데이터 손실 방지)와 함께 외부 공유 사용

외부 공유를 허용하지 않으면 비즈니스 요구 사항을 가지고 있는 사용자는 대체 도구 및 방법을 찾습니다. 중요한 기밀 파일을 보호하려면 외부 공유를 DLP 정책과 결합하는 것이 좋습니다.
  
### <a name="device-access-settings"></a>장치 액세스 설정

SharePoint및 OneDrive에 대한 장치 액세스 설정을 통해 액세스가 브라우저에만 제한되는지(파일을 다운로드할 수 없는지) 또는 액세스가 차단되는지 여부를 판단할 수 있습니다. 자세한 내용은 [관리되지 않는 장치에서의 액세스 제어](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)를 참조하세요. 

Azure Active Directory에서 권장된 조건부 액세스 정책을 사용하여 장치 액세스 설정을 사용하려면 [SharePoint 사이트 및 파일 보호을 위한 정책 권장 사항](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)을 참조하십시오.
  
이러한 설정을 방문하여 OneDrive 사이트에 대한 기본 설정을 변경할지 여부를 판단합니다. 현재 공유 및 장치 액세스 설정은 SharePoint 관리 센터에서 복제되어 두 환경 모두에 적용됩니다.
  
## <a name="team-and-sharepoint-site-configuration"></a>팀과 SharePoint 사이트 구성

다음의 표에서는 이 문서의 앞부분에서 설명한 각 팀과 그들의 기본 SharePoint 사이트에 대한 구성을 요약합니다. 이러한 구성을 시작하기 위한 권장 사항으로 사용하고, 조직의 요구 사항에 맞게 사이트 유형 및 구성을 조정합니다. 모든 조직에 모든 유형의 팀이 필요한 것은 아닙니다. 소수의 조직에만 극비 보호를 사용하는 팀이 필요합니다.
  
||||||
|:-----|:-----|:-----|:-----|:-----|
||**초기 보호 #1** <br/> |**초기 보호 #2** <br/> |**중요 보호** <br/> |**극비** <br/> |
|설명  <br/> |조직 내에서 검색 및 공동 작업을 허용하는 공개 팀.  <br/> |그룹 외부에서 기본 SharePoint 사이트의 공유가 허용되는 비공개 팀.  <br/> |기본 SharePoint 사이트의 공유가 사이트 구성원에게만 허용되는 비공개 팀 DLP는 조직 외부로 파일을 보내려고 할 때 사용자에게 경고합니다.  <br/> |파일과 함께 이동하는 파일 암호화 및 사용 권한에 대한 민감도 레이블을 사용하는 비공개 팀. DLP는 사용자가 조직 외부로 파일을 보내지 못하도록 방지합니다.  <br/> |
|개인 또는 공용 팀 사이트  <br/> |Public  <br/> |개인  <br/> |개인  <br/> |개인  <br/> |
|액세스 가능한 사용자  <br/> |B2B 사용자를 포함한 조직의 모든 사용자  <br/> |사이트 구성원만 - 다른 사용자는 액세스를 요청할 수 있습니다.  <br/> |팀의 구성원만. 다른 사용자는 팀 소유자가 승인하는 기본 사이트로의 액세스를 요청할 수 있습니다.  <br/> |구성원만. 다른 사용자는 기본 사이트로의 액세스를 요청할 수 없습니다.  <br/> |
|사이트 수준 공유 제어  <br/> |모든 사용자에게 공유가 허용됩니다. 기본 설정입니다.  <br/> |모든 사용자에게 공유가 허용됩니다. 기본 설정입니다.  <br/> |구성원은 사이트에 대한 액세스를 공유할 수 없습니다.  <br/> 구성원이 아닌 사용자는 사이트에 대한 액세스를 요청할 수 있지만, 팀의 그룹 소유자가 이러한 요청을 처리해야 합니다.  <br/> |구성원은 사이트에 대한 액세스를 공유할 수 없습니다.  <br/> 구성원이 아닌 사용자는 사이트 또는 사이트의 콘텐츠로의 액세스를 요청할 수 없습니다.  <br/> |
|사이트 수준 장치 액세스 제어  <br/> |추가 제어가 없습니다.  <br/> |추가 제어가 없습니다.  <br/> |사용자는 비호환 또는 비도메인 가입 장치로 파일을 다운로드할 수 없습니다. 이렇게 하면 다른 모든 장치에서 브라우저 전용으로 액세스할 수 있습니다.  <br/> |호환되지 않거나 도메인에 가입되지 않은 장치로의 파일 다운로드를 차단합니다.  <br/> |
|보존 레이블  <br/> |내부 공용  <br/> |개인  <br/> |중요  <br/> |극비  <br/> |
|DLP 정책  <br/> |||레이블이 중요 계층으로 지정된 파일을 조직 외부로 보낼 때 사용자에게 경고합니다.  <br/> 신용 카드 번호 또는 기타 개인 데이터와 같은 중요 데이터 형식의 외부 공유를 차단하기 위해 이러한 데이터 형식(구성한 사용자 지정 데이터 형식 포함)에 대한 추가 DLP 정책을 구성할 수 있습니다.  <br/> |사용자가 극비 계층으로 레이블이 지정된 파일을 외부 조직으로 보내지 못하도록 차단합니다. 사용자(파일을 공유하는 사용자 포함)는 근거를 제공하여 이 설정을 재정의할 수 있습니다.  <br/> |
|민감도 레이블  <br/> ||||민감도 레이블을 사용하여 파일에 대한 권한을 암호화하고 부여합니다. 파일이 기본 SharePoint 사이트에서 누출되는 경우 이러한 보호는 해당 파일과 함께 이동합니다.  <br/> |
   
네 가지 유형의 팀을 이 솔루션에 배포하는 단계는 [파일의 3단계 보호를 위한 팀 배포](deploy-teams-three-tiers.md)를 참조하세요.
  
## <a name="office-365-retention-labels"></a>Office 365 보존 레이블

중요 데이터가 있는 환경에서는 보존 레이블을 사용하는 것이 좋습니다. 보존 레이블을 구성하고 게시한 후 다음 작업을 수행할 수 있습니다.
  
- 팀의 기본 SharePoint 사이트에 있는 문서 라이브러리에 기본 레이블을 적용하여 팀의 **파일** 섹션에 있는 모든 문서에서 기본 레이블을 사용하도록 할 수 있습니다. 
    
- 특정 조건과 일치하는 경우 콘텐츠에 레이블을 자동으로 적용할 수 있습니다.
    
- 보존 레이블을 기준으로 하는 DLP 정책을 적용할 수 있습니다.
    
- 조직의 사용자는 웹용 Outlook, Outlook 2010 이상, OneDrive, SharePoint 및 Office 365 그룹의 콘텐츠에 수동으로 레이블을 적용할 수 있습니다. 사용자는 종종 자신이 사용하고 있는 콘텐츠의 형식을 가장 잘 알고 있기 때문에 콘텐츠를 분류하여 적절한 DLP 정책을 적용할 수 있습니다.
    
그림에서 보여 주듯이 이 솔루션에는 다음과 같은 보존 레이블 만들기가 포함됩니다.
  
- 극비
    
- 중요
    
- 개인
    
- 내부 공용
    
이러한 레이블은 이 문서의 앞부분에 있는 그림과 차트에서 권장된 사이트와 매핑됩니다. 이 솔루션에서 DLP 정책을 구성하여 중요 및 극비 레이블이 지정된 파일을 유출하지 못하도록 방지하는 것이 좋습니다.
  
이 솔루션에서 보존 레이블 및 DLP 정책을 구성하는 단계는 [보존 레이블 및 DLP(데이터 손실 방지)를 사용하여 팀의 파일 보호](deploy-teams-retention-DLP.md)를 참조하세요.
  
## <a name="sensitivity-labels"></a>민감도 레이블 

보안 시나리오에 적합한 경우 민감도 레이블을 사용하여 항상 파일에 수반되는 보호 기능을 적용할 수 있습니다. Microsoft 365 규정 준수 센터의 민감도 레이블과 Azure Information Protection 레이블은 동일합니다. 이 솔루션의 경우 민감도 레이블이나 하위 레이블을 사용하여 최고 수준의 보안으로 보호해야 하는 파일에 대한 권한을 암호화하고 부여하는 것을 권장합니다. 

자세한 내용은 [민감도 레이블 개요](../../compliance/sensitivity-labels.md)를 참조하세요.

이 솔루션에서 민감도 레이블을 구성하는 단계는 [민감도 레이블을 사용하여 팀에서의 파일 보호](deploy-teams-sensitivity-labels.md)를 참조하세요.
   
   
## <a name="see-also"></a>참고 항목
  
[클라우드 도입 및 하이브리드 솔루션](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
