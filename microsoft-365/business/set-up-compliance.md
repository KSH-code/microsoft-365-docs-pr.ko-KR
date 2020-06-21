---
title: Microsoft 365 Business Premium에 대 한 위협 보호 강화
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: 규정 준수 기능을 설정 하 여 데이터 손실을 방지 하 고 및 고객의 중요 한 정보를 안전 하 게 유지 합니다.
ms.openlocfilehash: 18886ff3a0ba5e99e63c70ef083d7a69c75bac91
ms.sourcegitcommit: e5bc49f0a25954d008b6cc09c2b98bb7bfe1aa2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785835"
---
# <a name="set-up-compliance-features"></a>준수 기능 설정

Microsoft 365 Business Premium에는 데이터와 장치를 보호 하는 기능이 제공 되며, 고객의 중요 한 정보를 안전 하 게 유지 하는 데 도움이 됩니다.

## <a name="set-up-dlp-features"></a>DLP 기능 설정

PII(개인 식별 정보)를 보호하도록 정책을 설정하는 방법의 예제를 보려면 [템플릿에서 DLP 정책 만들기](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template)를 참조하세요. 
  
DLP에는 다양 한 로캘에 대 한 다양 한 사용 가능 정책 템플릿이 제공 됩니다. 예를 들어 오스트레일리아 재무 데이터, 캐나다 개인 정보 Act, 미국 재무 데이터 등이 있습니다. 전체 목록에 대해 [DLP 정책 템플릿에 포함 된 내용을](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) 확인 합니다. 이러한 서식 파일은 모두 PII 서식 파일 예제와 비슷하게 설정할 수 있습니다. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Exchange Online Archiving을 사용하여 전자 메일 보존 설정

 **Exchange Online 보관** 라이선스 기능은 eDiscovery에 대 한 전자 메일 콘텐츠를 보존 하 여 준수 및 규제 표준을 유지 관리 하는 데 도움이 됩니다. 또한 서 소송이가 있는 경우 위험을 줄이고, 보안 위반 후 또는 삭제 된 항목을 복구 해야 하는 경우 데이터를 복구할 수 있는 방법을 제공 합니다. 소송 보존을 사용 하 여 모든 사용자의 콘텐츠를 보존 하거나 보존 정책을 사용 하 여 보존 하려는 항목을 사용자 지정할 수 있습니다.
  
**소송 보존:** 사용자의 전체 사서함에 소송 보존을 적용하여 삭제한 항목을 포함하는 모든 사서함 콘텐츠를 보존할 수 있습니다. 
    
사서함에 소송 보존을 적용하려면 관리 센터에서 다음을 수행합니다.
    
1. 왼쪽 탐색 영역에서 **사용자** \> **활성 사용자**로 이동합니다.
    
2. 사서함에 소송 보존을 적용 하려는 사용자를 선택 합니다. 사용자 창에서 **메일 설정을**확장 하 고 **기타 설정**옆에 있는 **Exchange 속성 편집**을 선택 합니다.
    
3. 사용자의 사서함 페이지에서 왼쪽 탐색 영역의 ** 사서함 기능**을 선택하고 **소송 보존** 아래의 **사용** 링크를 선택합니다.
    
4. **소송** 보존 대화 상자의 소송 보존 **기간** 필드에 소송 보존 기간을 지정할 수 있습니다. 무기한 유지 하려면 필드를 비워 둡니다. 메모를 추가 하 고 사서함 소유자에 게 소송 보존에 대 한 자세한 내용을 설명 해야 할 수 있는 웹 사이트로 지시할 수도 있습니다. \>**저장**을 합니다.
    
**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period. To learn more, see [Overview of retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies).

## <a name="set-up-sensitivity-labels"></a>민감도 레이블 설정

민감도 레이블은 Azure Information Protection (AIP) 계획 1에 제공 되며, 레이블을 적용 하 여 문서와 전자 메일을 분류 하 고 필요에 따라 보호할 수 있습니다. 규칙 및 조건을 정의 하는 관리자가 사용자에 의해 수동으로 또는 사용자에 게 권장 사항을 제공 하는 조합을 사용 하 여 레이블을 자동으로 적용할 수 있습니다.

민감도 레이블을 설정 하려면 [만들기 및 관리 민감도 레이블](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) 비디오를 확인 합니다.



### <a name="install-the-azure-information-protection-client-manually"></a>수동으로 Azure Information Protection 클라이언트 설치

AIP 클라이언트를 수동으로 설치하려면

1. [Microsoft 다운로드 센터](https://www.microsoft.com/download/details.aspx?id=53018)에서 **AzinfoProtection_UL.exe** 를 다운로드 합니다.
 
2. Word 문서를 보고 **홈** 탭에서 **민감도** 옵션을 사용할 수 있는지 확인 하 여 설치가 제대로 되었는지 확인할 수 있습니다.
<br/>![Word 문서의 보호 탭 드롭다운](../media/word-sensitivity.png)

자세한 내용은 [클라이언트 설치](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)를 참조 하세요.
