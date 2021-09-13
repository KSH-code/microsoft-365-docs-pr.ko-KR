---
title: 보안 위협에 대한 위협 Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: 규정 준수 기능을 설정하여 데이터 손실을 방지하고 사용자와 고객의 중요한 정보를 안전하게 보호합니다.
ms.openlocfilehash: 5e5aff344326874cef426e7a1a40656766564e7e
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59186795"
---
# <a name="set-up-compliance-features"></a>준수 기능 설정

사용자 Microsoft 365 Business Premium 및 장치를 보호하고 사용자와 고객의 중요한 정보를 안전하게 유지하는 데 도움이 되는 기능이 함께 제공되어 있습니다.

## <a name="set-up-dlp-features"></a>DLP 기능 설정

개인 [데이터 손실을](../../compliance/create-a-dlp-policy-from-a-template.md) 방지하는 정책을 설정하는 방법에 대한 예제는 템플릿에서 DLP 정책 만들기를 참조합니다. 
  
DLP는 다양한 로 로컬에 대해 즉시 사용할 수 있는 많은 정책 템플릿과 함께 제공합니다. 예를 들어 오스트레일리아 재무 데이터, 캐나다 개인 정보법, 미국 재무 데이터 등입니다. 전체 [목록은 DLP 정책 템플릿에](../../compliance/what-the-dlp-policy-templates-include.md) 포함된 것을 참조하세요. 이러한 모든 템플릿은 PII 템플릿 예제와 유사하게 사용하도록 설정될 수 있습니다. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Exchange Online Archiving을 사용하여 전자 메일 보존 설정

 **Exchange Online Archiving** 라이선스 기능은 eDiscovery에 대한 전자 메일 콘텐츠를 보존하여 규정 준수 및 규정 표준을 유지하는 데 도움이 됩니다. 또한 소송이 있는 경우 위험을 줄이는 데 도움이 되고, 보안 위반 후 또는 삭제된 항목을 복구해야 할 때 데이터를 복구할 수 있는 방법을 제공합니다. 소송 보존을 사용하여 사용자의 모든 콘텐츠를 보존하거나 보존 정책을 사용하여 보존할 콘텐츠를 사용자 지정할 수 있습니다.
  
**소송 보존:** 사용자의 전체 사서함에 소송 보존을 적용하여 삭제한 항목을 포함하는 모든 사서함 콘텐츠를 보존할 수 있습니다. 
    
사서함에 소송 보존을 적용하려면 관리 센터에서 다음을 수행합니다.
    
1. 왼쪽 탐색 영역에서 **사용자** \> **활성 사용자** 로 이동합니다.
    
2. 사서함에 소송을 보류할 사용자를 선택합니다. 사용자 창에서 메일 설정 을 확장하고 추가 설정 옆에 **있는** 속성 **편집을 Exchange 선택합니다.**
    
3. 사용자의 사서함 페이지에서 왼쪽 탐색 영역의 ** 사서함 기능**을 선택하고 **소송 보존** 아래의 **사용** 링크를 선택합니다.
    
4. 소송  보유 대화 상자에서 소송 보유 기간 필드에 소송 보유 기간을 **지정할 수** 있습니다. 무한 보류를 하려는 경우 필드를 비워 두면 됩니다. 또한 메모를 추가하고 사서함 소유자를 소송 보류에 대해 더 설명해야 할 수 있는 웹 사이트에 지시할 수도 있습니다. \>**를 저장합니다.**
    
**보존:** 특정 기간 동안 보존하거나 보존 기간이 끝나면 영구적으로 콘텐츠를 삭제하는 것과 같은 사용자 지정된 보존 정책을 사용하도록 설정할 수 있습니다. 자세한 내용은 [보존 정책 개요](../../compliance/retention.md)를 참조하세요.

## <a name="set-up-sensitivity-labels"></a>민감도 레이블 설정

민감도 레이블은 AIP(Azure Information Protection) 플랜 1과 함께 제공되어 레이블을 적용하여 문서 및 전자 메일을 분류하고 선택적으로 보호하는 데 도움이 됩니다. 규칙 및 조건을 정의하는 관리자가 레이블을 자동으로 적용하거나, 사용자가 수동으로 또는 사용자에게 권장 사항을 제공한 조합을 사용하여 레이블을 적용할 수 있습니다.

민감도 레이블을 설정하기 위해 민감도 레이블 비디오를 만들고 [관리합니다.](../../business-video/create-sensitivity-labels.md)



### <a name="install-the-azure-information-protection-client-manually"></a>수동으로 Azure Information Protection 클라이언트 설치

AIP 클라이언트를 수동으로 설치하려면

1. Microsoft **AzinfoProtection_UL.exe** [센터에서 다운로드할 수 있습니다.](https://www.microsoft.com/download/details.aspx?id=53018)
 
2. Word 문서를 보고 홈 탭에서 민감도 옵션을 사용할  수 있는지 확인하여 설치가 완료된지 **확인할 수** 있습니다.
<br/>![Word 문서의 보호 탭 드롭다운](../../media/word-sensitivity.png)

자세한 내용은 [클라이언트 설치를 참조하세요.](/azure/information-protection/infoprotect-tutorial-step3)