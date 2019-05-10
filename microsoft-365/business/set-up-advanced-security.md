---
title: Microsoft 365 비즈니스 사용자를 위한 고급 보안 정책 설정
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
ms.openlocfilehash: 4728e11a16fdf8a461f5687632df75699923f846
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "33663650"
---
# <a name="set-up-advanced-security-policies"></a>고급 보안 정책 설정

[관리 센터](security-features.md#microsoft-365-business-admin-center-security-features)에서 설정할 수 있는 정책 외에도 [Office 365 ATP (Advanced Threat protection](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653) )를 설정 하 여 사이버 위협에 대 한 추가 보호 기능을 추가할 수 있습니다. 또한 DLP ( [데이터 손실 방지](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e) ), Aip (Azure information Protection), [Exchange Online 보관](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)및 [Intune 포털](#go-to-intune-admin-center)에서 장치 관리를 설정 하 여 중요 한 정보를 보호할 수 있습니다.

[Microsoft 365 비즈니스 계획의 보안을 유지 하](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) 는 가장 중요 한 방법에 대 한 개요를 확인 하려면 다음을 참조 하세요 (예를 들어, MFA를 사용 하 여 두 번째 형태의 로그인을 만드는 경우).

보다 쉬운 지침을 보려면 [비즈니스 교육 비디오의 보안](https://support.office.com/article/e12187b8-216a-4490-9e3b-df34a06fb787) 을 참조 하세요.

## <a name="increase-email-malware-protection"></a>전자 메일 맬웨어 방지 기능 향상

맬웨어는 컴퓨터나 네트워크에 손상을 줄 수 있으며 개인 또는 고객 정보를 포함 하 여 사용자의 데이터를 훔 치기 위해 발생 하는 소프트웨어입니다. Microsoft 365 Business에는 맬웨어에 대 한 기본 보호 수준이 포함 되어 있지만 추가 설정을 설정 하 여이 보호를 강화할 수 있습니다. 자세한 내용은 [맬웨어 검색 교육 비디오 켜기를](https://support.office.com/article/02b5783a-eea0-42e8-8856-62440718c3f0) 참조 하세요.

## <a name="set-up-advanced-threat-protection-features"></a>Advanced Threat Protection 기능 설정

- **안전 하지 않은 첨부 파일을 보호 합니다.** ATP는 가상 환경에서 전자 메일 첨부 파일을 열고 결과 동작에 대 한 분석을 수행 하 여 악의적인 콘텐츠를 식별 합니다. 콘텐츠를 평가 하 여 정규 또는 악성의 의도를 확인 하 고 ATP가 안전 하지 않은 첨부 파일의 배달을 차단 하 여 피싱 체계 및 랜 섬 웨어 감염 으로부터 사용자를 보호 합니다. 첨부 파일 보호를 활성화 하려면 [Office 365 ATP 안전한 첨부 파일을 설정](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775) 하 고 [악성 파일에 대 한 보호](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5) 간단한 교육 비디오를 참조 하세요.
    
- **사용자가 악의적인 링크를 클릭 하면 환경을 보호 합니다.** ATP는 사용자가 전자 메일을 클릭할 때 링크를 검사 하기도 합니다. 링크가 안전 하지 않은 경우 사용자에 게 사이트를 방문 하지 않거나 사이트가 차단 되었음을 알리는 경고가 표시 됩니다. 이를 통해 피싱 수법을 방지할 수 있습니다. 이를 활성화 하려면 [Office 365 ATP 안전한 링크 설정](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-atp-safe-links-policies) 도움말 설명서 및 [악의적인 사이트에 대 한 보호](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa) 간단한 교육 비디오를 참조 하세요.

- **피싱 시도 로부터 환경을 보호 합니다.**  ATP 바이러스 방지는 일련의 컴퓨터 학습 모델 집합을 들어오는 메시지에 적용 하 여, 누군가가 사용자 로부터 정보를 추출 하려고 하는 피싱 공격 으로부터 보호를 제공 합니다. 부서. 이를 활성화 하려면 [ATP 피싱 방지](https://docs.microsoft.com/office365/securitycompliance/set-up-anti-phishing-policies) 도움말 설명서를 설정 하 고 [피싱 시도 로부터 보호](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c) 간단한 교육 비디오를 참조 하세요.

## <a name="set-up-dlp-features"></a>DLP 기능 설정

PII(개인 식별 정보)를 보호하도록 정책을 설정하는 방법의 예제를 보려면 [템플릿에서 DLP 정책 만들기](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369)를 참조하세요. 
  
DLP는 사용 준비가 완료된 여러 다른 로캘용 정책 템플릿을 제공합니다. 예를 들어, 오스트레일리아 재무 데이터, 캐나다 개인 정보 보호법, 미국 재무 데이터 등이 있습니다. 전체 목록을 보려면 [DLP 정책 템플릿에 포함되는 내용](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a)을 참조하세요. 이러한 모든 템플릿은 PII 템플릿 예제와 비슷한 방식으로 사용하도록 설정할 수 있습니다. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Exchange Online Archiving을 사용하여 전자 메일 보존 설정

 **Exchange Online Archiving** 라이선스 기능을 사용하면 eDiscovery 목적에 맞게 전자 메일 콘텐츠를 보존하여 규정 준수 및 규정 표준을 유지 관리할 수 있습니다. 그뿐 아니라 소송이 발생할 경우 위험 요소를 줄일 수 있으며 보안 위반 이후나 삭제한 항목을 복구해야 할 경우에 복구하는 방법도 제공됩니다. 이러한 기능을 활성화하려면 소송 보존을 사용하여 모든 사용자의 콘텐츠를 보존하거나 보다 나은 사용자 지정을 위해 보존 정책을 사용할 수 있습니다. 
  
**소송 보존:** 사용자의 전체 사서함에 소송 보존을 적용하여 삭제한 항목을 포함하는 모든 사서함 콘텐츠를 보존할 수 있습니다. 
    
사서함에 소송 보존을 적용하려면 관리 센터에서 다음을 수행합니다.
    
1. 왼쪽 탐색 영역에서 **사용자** \> **활성 사용자**로 이동합니다.
    
2. 해당 사서함에 소송 보존을 적용하려는 사용자를 선택하고 사용자 창에서 **메일 설정**을 확장하고 **기타 설정** 옆에 있는 **Exchange 속성 편집**을 선택합니다.
    
3. 사용자의 사서함 페이지에서 왼쪽 탐색 영역의 ** 사서함 기능**을 선택하고 **소송 보존** 아래의 **사용** 링크를 선택합니다.
    
4. **소송 보존** 대화 상자의 **소송 보존 기간** 필드에서 소송 보존 기간을 지정할 수 있습니다. 무한 보존을 적용하려면 이 필드를 비워 둡니다. 메모를 추가하여 사서함 소유자에게 소송 보존 \>에 대해 추가로 설명해야 하는 웹 사이트를 알려주고 **저장**을 선택합니다.
    
**보존:** 특정 기간 동안 보존하거나 보존 기간이 끝나면 영구적으로 콘텐츠를 삭제하는 것과 같은 사용자 지정된 보존 정책을 사용하도록 설정할 수 있습니다. 자세한 내용은 [보존 정책 개요](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)를 참조하세요.
## <a name="set-up-azure-information-protection-features"></a>Azure Information Protection 기능 설정

AIP(Azure Information Protection)는 조직에서 레이블을 적용하여 해당 문서 및 전자 메일을 분류하고 필요에 따라 보호할 수 있도록 하는 클라우드 기반 솔루션입니다. 이러한 레이블은 규칙 및 조건을 정의하는 관리자가 자동으로 적용하거나, 사용자가 수동으로 적용하거나, 사용자에게 권장 사항을 제공하는 상황에서 두 가지 방법을 조합하여 적용할 수 있습니다.

웹용 Outlook에서 전자 메일을 보낼 경우 모든 사용자가 다음과 같은 제한을 적용할 수 있게 자동으로 설정됩니다.
  
- **전달 금지**: 받는 사람은 메시지를 읽을 수 있지만 콘텐츠를 전달, 인쇄 또는 복사할 수 없습니다
    
- **암호화**: 전체 메시지가 암호화됩니다. 받는 사람은 암호화된 콘텐츠에 액세스하기 전에 추가 단계를 수행하여 해당 ID를 확인해야 하며 암호화를 제거할 수 없습니다.
    
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

## <a name="go-to-intune-admin-center"></a>Intune 관리 센터로 이동합니다.

1. [Azure Portal](https://portal.azure.com/)에 로그인합니다.

2. **모든 서비스**를 선택하고 **검색 상자**에 *Intune*을 입력합니다.

3. 결과가 표시되면 **Microsoft Intune** 옆에 있는 시작을 클릭하여 즐겨찾기로 지정하고 나중에 쉽게 찾을 수 있습니다.

관리 센터 외에도 Intune을 사용 하 여 조직의 장치를 등록 하 고 관리할 수 있습니다. 자세한 내용은 [Windows 장치용 등록 방법](https://docs.microsoft.com/intune/enrollment-method-capabs) 및 [Intune으로 관리 되는 장치에 대 한 등록 옵션](https://docs.microsoft.com/intune/enrollment-options)의 기능을 참조 하세요.

## <a name="microsoft-secure-score"></a>Microsoft Secure Score

