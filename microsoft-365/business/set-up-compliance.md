---
title: Microsoft 365 Business에 대 한 위협 요소 보호 강화
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
search.appverid:
- BCS160
- MET150
description: Office 365 Advanced Threat Protection을 설정 하 고 중요 한 데이터를 보호 합니다.
ms.openlocfilehash: 53741a7726222bb32329a401953be72257df95cc
ms.sourcegitcommit: 7ac06563c6ff034358e8fd3f9298fc426187ade2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668399"
---
# <a name="set-up-compliance-features"></a>규정 준수 기능 설정

Microsoft 365 Business에는 데이터 및 장치를 보호 하기 위한 기능이 제공 되며, 사용자와 고객의 중요 한 정보를 안전 하 게 유지 하는 데 도움이 됩니다.

## <a name="set-up-dlp-features"></a>DLP 기능 설정

PII(개인 식별 정보)를 보호하도록 정책을 설정하는 방법의 예제를 보려면 [템플릿에서 DLP 정책 만들기](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369)를 참조하세요. 
  
DLP는 사용 준비가 완료된 여러 다른 로캘용 정책 템플릿을 제공합니다. 예를 들어, 오스트레일리아 재무 데이터, 캐나다 개인 정보 보호법, 미국 재무 데이터 등이 있습니다. 전체 목록을 보려면 [DLP 정책 템플릿에 포함되는 내용](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a)을 참조하세요. 이러한 모든 템플릿은 PII 템플릿 예제와 비슷한 방식으로 사용하도록 설정할 수 있습니다. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Exchange Online Archiving을 사용하여 전자 메일 보존 설정

 **Exchange Online 보관** 라이선스 기능은 eDiscovery에 대 한 전자 메일 콘텐츠를 보존 하 여 준수 및 규제 표준을 유지 관리 하는 데 도움이 됩니다. 또한 서 소송이의 이벤트로 인 한 위험을 줄이고, 보안 위반 후 또는 삭제 된 항목을 복구 해야 하는 경우 데이터를 복구할 수 있는 방법을 제공 합니다. 소송 보존을 사용 하 여 모든 사용자의 콘텐츠를 보존 하거나 보존 정책을 사용 하 여 보존 하려는 항목을 사용자 지정할 수 있습니다.
  
**소송 보존:** 사용자의 전체 사서함에 소송 보존을 적용하여 삭제한 항목을 포함하는 모든 사서함 콘텐츠를 보존할 수 있습니다. 
    
사서함에 소송 보존을 적용하려면 관리 센터에서 다음을 수행합니다.
    
1. 왼쪽 탐색 영역에서 **사용자** \> **활성 사용자**로 이동합니다.
    
2. 해당 사서함에 소송 보존을 적용하려는 사용자를 선택하고 사용자 창에서 **메일 설정**을 확장하고 **기타 설정** 옆에 있는 **Exchange 속성 편집**을 선택합니다.
    
3. 사용자의 사서함 페이지에서 왼쪽 탐색 영역의 ** 사서함 기능**을 선택하고 **소송 보존** 아래의 **사용** 링크를 선택합니다.
    
4. **소송 보존** 대화 상자의 **소송 보존 기간** 필드에서 소송 보존 기간을 지정할 수 있습니다. 무한 보존을 적용하려면 이 필드를 비워 둡니다. 메모를 추가하여 사서함 소유자에게 소송 보존 \>에 대해 추가로 설명해야 하는 웹 사이트를 알려주고 **저장**을 선택합니다.
    
**보존:** 특정 기간 동안 보존하거나 보존 기간이 끝나면 영구적으로 콘텐츠를 삭제하는 것과 같은 사용자 지정된 보존 정책을 사용하도록 설정할 수 있습니다. 자세한 내용은 [보존 정책 개요](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)를 참조하세요.

## <a name="set-up-azure-information-protection-features"></a>Azure Information Protection 기능 설정

AIP (Azure Information Protection)를 사용 하면 레이블을 적용 하 여 문서와 전자 메일을 분류 하 고 선택적으로 보호할 수 있습니다. 규칙 및 조건을 정의 하는 관리자가 사용자에 의해 수동으로 또는 사용자에 게 권장 사항을 제공 하는 조합을 사용 하 여 레이블을 자동으로 적용할 수 있습니다.

웹용 Outlook에서 전자 메일에 다음과 같은 기본 제공 레이블 및 제한을 적용할 수 있습니다.
  
- **전달 금지**: 받는 사람은 메시지를 읽을 수 있지만 콘텐츠를 전달, 인쇄 또는 복사할 수 없습니다
    
- **Encrypt**: 전체 메시지가 암호화 됩니다. 받는 사람은 암호화 된 콘텐츠에 액세스 하기 전에 해당 id를 확인 해야 하며 암호화를 제거할 수 없습니다.
    
- **기밀**: 조직의 직원들에게 전자 메일 콘텐츠 및 첨부 파일에 대한 모든 권한을 부여하지만, 조직 외부의 사람에게는 이러한 권한을 부여하지 않습니다. 데이터 소유자는 언제든지 콘텐츠를 추적하고 취소할 수 있습니다.
    
- **극비**: 이 제한은 극비 데이터에 적용할 수 있으며, 직원들이 데이터를 보고, 편집하고, 회신할 수 있지만 전달, 인쇄 또는 복사할 수는 없도록 합니다. 데이터 소유자는 언제든지 콘텐츠를 추적하고 취소할 수 있습니다.

### <a name="make-sure-azure-information-protection-is-activated"></a>Azure Information Protection이 활성화되어 있는지 확인

AIP가 활성화되었는지 확인하려면

1. [Azure Portal](https://portal.azure.com/)에 로그인합니다.

2. **모든 서비스**를 선택하고 **검색 상자**에 *Azure Information Protection*을 입력합니다.

3. 결과가 표시되면 **Azure Information Protection** 옆에 있는 시작을 클릭하여 즐겨찾기로 지정하고 나중에 쉽게 찾을 수 있습니다.

4. **Azure Information Protection** \> **보호 활성화**를 선택하고 상태가 활성화됨으로 설정되어 있는지 확인합니다. 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a>Azure Information Protection 정책 및 기본 레이블 보기 

기존 레이블을 보고 수정하려면

1. Azure Information Protection 대시보드에서 **분류** \> **레이블**을 선택합니다. <br/>![Azure Information Protection의 표준 레이블](media/AIPLabels.png)

2. 옵션을 보려면 아무 레이블이나 선택합니다. 표시 이름, 색 등을 변경할 수 있습니다.
 
3. 고유한 레이블을 만들려면 [레이블 수정 및 새로 만들기](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2)를 참조하세요. 

### <a name="install-the-azure-information-protection-client-manually"></a>수동으로 Azure Information Protection 클라이언트 설치

AIP 클라이언트를 수동으로 설치하려면

1. [Microsoft 다운로드 센터](https://www.microsoft.com/download/details.aspx?id=53018)에서 **AzInfoProtection.exe**를 다운로드합니다.
 
2. Word 문서를 보고 **홈** 탭에서 **보호** 옵션을 사용할 수 있는지 확인하여 설치가 제대로 되었는지 확인할 수 있습니다. <br/>![Word 문서의 보호 탭 드롭다운](media/Word_Protect.png)

자세한 내용은 [클라이언트 설치](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)를 참조 하세요.
