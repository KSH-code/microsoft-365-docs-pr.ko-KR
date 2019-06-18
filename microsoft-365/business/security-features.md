---
title: Microsoft 365 Business 보안 및 규정 준수 기능
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-security-compliance
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Microsoft 365 Business에 제공되는 보안 기능에 대해 알아봅니다.
ms.openlocfilehash: bd61ad3bf1b34635a7b80f1c9ccf63fa98d31915
ms.sourcegitcommit: 274af83139ad7da3aa33366c3323d533d95c7db4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2019
ms.locfileid: "35017525"
---
# <a name="microsoft-365-business-security-and-compliance-features"></a>Microsoft 365 Business 보안 및 규정 준수 기능

Microsoft 365 Business는 PC, 휴대폰 및 태블릿의 데이터를 보호하기 간편한 보안 기능을 제공합니다.
    
## <a name="microsoft-365-business-admin-center-security-features"></a>Microsoft 365 Business 관리 센터 보안 기능

![를 https://aka.ms/aboutM365preview가리키는 배너입니다.](media/m365admincenterchanging.png)

관리 센터에서 다양한 Microsoft 365 Business 보안 기능을 간편하게 설정 또는 해제하면서 편리하게 관리할 수 있습니다. 관리 센터에서는 다음을 수행할 수 있습니다.
  
  
- [Android 또는 iOS 디바이스에 대한 애플리케이션 관리 설정 지정](app-protection-settings-for-android-and-ios.md). 
    
    이러한 설정을 통해 지정된 기간 후에 비활성 상태인 디바이스에서 파일을 삭제하고, 작업 파일을 암호화하고, 사용자가 PIN 등을 설정하도록 요구할 수 있습니다.
    
- [Windows 10 디바이스의 애플리케이션 설정 지정](protection-settings-for-windows-10-devices.md) 
    
    이러한 설정은 회사 소유 또는 개인 소유의 디바이스에 있는 회사 데이터에 적용될 수 있습니다.
    
- [Windows 10 디바이스의 디바이스 보호 설정 지정](protection-settings-for-windows-10-pcs.md). 
    
    [BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405) 암호화를 사용하도록 설정하여 디바이스를 분실하거나 도난당한 경우 데이터를 보호하고, [Windows Exploit Guard](https://go.microsoft.com/fwlink/p/?linkid=871404)를 사용하도록 설정하여 랜섬웨어에 대한 고급 보호 기능을 제공할 수 있습니다. 
    
- [장치에서 회사 데이터 제거](remove-company-data.md)
    
    디바이스를 분실하거나 도난당한 경우 또는 직원이 퇴사하는 경우 회사 데이터를 원격으로 지울 수 있습니다.
    
- [Windows 10 디바이스를 공장 설정으로 다시 설정](reset-devices-to-factory-settings.md). 
    
    디바이스 보호가 설정된 Windows 10 디바이스를 다시 설정할 수 있습니다.
    
## <a name="additional-security-features"></a>추가 보안 기능 

Microsoft 365 Business의 고급 기능을 사용하여 사이버 위협으로부터 비즈니스를 보호하고 중요한 정보를 보호할 수 있습니다.
  
- **[Office 365 Advanced Threat Protection](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)**
    
    ATP(Advanced Threat Protection)는 직원이나 고객 정보를 손상시키도록 설계된 정교한 피싱 및 랜섬웨어 공격으로부터 비즈니스를 보호할 수 있도록 합니다.기능은 다음과 같습니다.
    
  - 위험한 메시지를 감지하고 삭제하기 위한 정교한 첨부 파일 검색 및 AI 기반 분석
    
  - 전자 메일의 링크를 자동으로 확인 하 여 피싱 체계의 일부인 경우 평가 합니다. 이렇게 하면 안전 하지 않은 웹 사이트에 안전 하 게 액세스할 수 없습니다.

- **[Azure Portal의 Intune 전체 기능](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    Azure Portal에서 Intune 관리 센터에 액세스하여 Microsoft 365 Business 관리 센터를 통해 사용할 수 없는 Windows용 고급 디바이스 관리와 함께 MacOS 디바이스, iPhone 및 Android 디바이스 관리와 같은 추가 보안 기능을 설정할 수 있습니다.
- **Azure AD P1 계획과 동일한 [조건부 액세스](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/overview)**

    조건부 액세스를 사용 하면 조직에서 로그인 위험 으로부터 보호 하 고, 예기치 않은 네트워크 또는 로캘에서 액세스를 시도 하 고, access에서 위험한 장치 유형을 형성 하는 등의 방법을 사용할 수 있습니다. 조건부 액세스 정책은 첫 번째 인증을 완료 한 후에 적용 되며 첫 번째 인증 이벤트의 신호를 사용 하 여 시도 된 액세스를 승인, 거부 또는 f 추가 증명 (예: 두 번째 유형의 식별)으로 할지 결정 합니다. 필수.

    다음과 같은 조건부 액세스 기능이 포함 되어 있습니다.

    - 사용자 이름, 그룹 및 역할을 기반으로 액세스
    - [앱을 기반으로 하는](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access) 액세스 
    - [위치를 기반으로 액세스](https://docs.microsoft.com/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration)  신뢰할 수 있는 IP 범위 또는 특정 국가 에서만 액세스 허용 
    - 액세스를 위해 MFA 필요
    - [레거시 인증](https://docs.microsoft.com/azure/active-directory/conditional-access/block-legacy-authentication) 을 사용 하는 앱에 대 한 액세스 차단
    - 앱 tp에 [Intune 앱 보호](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access) 사용
    - 타사 공급자가 포함 된 MFA와 같은 사용자 지정 인증 (예: DUO)
   
    기타 기능:
    - 하이브리드 Azure AD에 대 한 [셀프 서비스 암호 재설정](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-customization)
    
## <a name="compliance-features"></a>준수 기능

Microsoft 365 비즈니스 구독에는 준수 및 규정 표준을 유지 관리 하는 데 도움이 되는 기능이 포함 되어 있습니다.

- **[데이터 손실 방지 정책 개요](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)**(DLP) 
    
    신용 카드 번호, 주민 등록 번호 등의 중요한 정보를 자동으로 감지하도록 DLP를 설정하여 회사 외부에서 함부로 공유하는 일을 방지할 수 있습니다.
    
- **[Exchange Online Archiving](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Exchange Online Archiving 라이선스가 있으면 연속 데이터 백업을 사용하여 메시지를 쉽게 보관할 수 있습니다. 이 기능은 나중에 검색 또는 복원에 필요한 경우에 대비하여 삭제한 항목을 포함하는 모든 사용자 전자 메일을 저장합니다. 또한 소송 보존, eDiscovery을 위해 전자 메일 데이터를 보존하거나 규정 준수 요구 사항을 충족할 수 있습니다.
    
- **[Azure Information Protection](https://go.microsoft.com/fwlink/p/?linkid=871406)**
    
    정보 보호를 사용 하면 "전달 금지" 및 "복사 금지"와 같은 컨트롤을 사용 하 여 전자 메일 및 문서에서 중요 한 정보에 대 한 액세스를 제어할 수 있습니다. 중요 한 정보를 "기밀"으로 분류 하 고 분류 된 정보를 비즈니스 외부 및 내부에 공유 하는 방법을 지정할 수도 있습니다. 엔터프라이즈 등급 암호화는 전자 메일 및 문서에 쉽게 적용할 수 있으며 정보를 비공개로 유지 하는 데 사용 됩니다. Microsoft 365 Business에는 [Azure Information Protection 계획 1](https://go.microsoft.com/fwlink/p/?linkid=871407)의 모든 기능이 포함 되어 있습니다. Office 용 Azure Information Protection 클라이언트 추가 기능을 설치할 수도 있습니다. 자세한 내용은 [Azure Information Protection 클라이언트 관리자 가이드](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide)를 참조 하세요.

이러한 기능은 보안 &amp; 및 준수 센터 및 Intune 관리 센터에서 관리할 수 있습니다. 시간이 지남에 따라 간소화 된 컨트롤이 Microsoft 365 비즈니스 관리 센터에 추가 됩니다.
  
    
## <a name="faq"></a>FAQ

 ### <a name="are-these-security-features-available-in-all-markets"></a>이러한 보안 기능을 모든 지역/국가에서 사용할 수 있나요?
  
예. 이러한 기능은 Microsoft 365 Business가 판매되는 모든 지역/국가에서 사용할 수 있습니다.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>보안 및 준수 센터는 어떻게 찾을 수 있나요?
  
1. 관리자 자격 증명을 사용하여 [Microsoft 365 Business에 로그인](https://portal.microsoft.com/)합니다. 
    
2. 왼쪽 탐색 창에서 **관리 센터**를 찾아 확장합니다. 
    
    ![Microsoft 365 관리 센터의 왼쪽 탐색 창에서 관리 센터를 선택합니다.](media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. **보안 및 준수**를 선택하여 보안 및 준수 센터로 이동합니다.