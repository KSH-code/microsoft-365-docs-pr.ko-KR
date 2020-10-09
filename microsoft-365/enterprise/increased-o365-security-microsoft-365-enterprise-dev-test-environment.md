---
title: 엔터프라이즈 테스트 환경용 Microsoft 365에 대 한 Microsoft 365 보안 강화
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 이 테스트 랩 가이드를 사용 하 여 추가 Microsoft 365 보안 설정 (엔터프라이즈 테스트 환경에 대해 Microsoft 365)을 사용 하도록 설정 합니다.
ms.openlocfilehash: 09a613261bc173cd71e9cc2dd58a32a9547ece21
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48398952"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a>엔터프라이즈 테스트 환경용 Microsoft 365에 대 한 Microsoft 365 보안 강화

*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경용 Microsoft 365에만 사용할 수 있습니다.*

이 문서의 지침을 사용 하 여 microsoft 365 (엔터프라이즈 테스트 환경)에서 보안을 강화 하도록 Microsoft 365 설정을 추가로 구성 합니다.

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [여기](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축

최소 요구 사항에 따라 간단한 방법으로 Microsoft 365 보안 강화를 구성 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.
  
시뮬레이트된 엔터프라이즈에서 Microsoft 365 보안 향상을 구성 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.
  
> [!NOTE]
> 테스팅 Microsoft 365 security에서는 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경을 필요로 하지 않습니다. 이 기능은 자동 라이선스 및 그룹 구성원을 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트할 수 있도록 옵션으로 제공 됩니다. 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>2 단계: 향상 된 Microsoft 365 보안 구성

이 단계에서는 엔터프라이즈 테스트 환경용 Microsoft 365에 대 한 Microsoft 365 보안 향상을 사용 하도록 설정 합니다. 추가 정보 및 설정에 대 한 자세한 내용은 [보안 강화를 위해 테 넌 트 구성을](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)참조 하십시오.

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>최신 인증을 지원 하지 않는 앱을 차단 하도록 SharePoint Online 구성

최신 인증을 지원 하지 않는 앱에는 [id 및 장치 액세스 구성을](../security/office-365-security/microsoft-365-policies-configurations.md) 적용할 수 없으며,이는 Microsoft 365 구독 및 디지털 자산의 보안을 유지 하는 중요 한 요소입니다. 

1. Microsoft 365 관리 센터 ()로 이동 하 [https://portal.microsoft.com](https://portal.microsoft.com) 고 전역 관리자 계정을 사용 하 여 microsoft 365 테스트 랩 구독에 로그인 합니다.
    
  - 경량 Microsoft 365 테스트 환경을 사용 하는 경우 로컬 컴퓨터에서 로그인 합니다.
    
  - 시뮬레이트된 엔터프라이즈 Microsoft 365 테스트 환경을 사용 하는 경우 [Azure portal](https://portal.azure.com) 을 사용 하 여 client1 가상 컴퓨터에 연결한 다음 client1에서 로그인 합니다.
 
2. 새 **Microsoft 365 관리 센터** 탭의 왼쪽 탐색 창에 있는 **관리 센터** 에서 **SharePoint**를 클릭 합니다.
3. 새 **SharePoint 관리 센터** 탭에서 **정책 > 액세스 제어**를 클릭 합니다.
4. **최신 인증을 지원 하지 않는 앱**을 클릭 하 고 **액세스 차단을**선택한 다음 **저장**을 클릭 합니다.


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>SharePoint, 비즈니스용 OneDrive 및 Microsoft 팀에 대해 Advanced Threat Protection을 사용 하도록 설정

SharePoint, OneDrive 및 Microsoft 팀의 Office 365 Advanced Threat Protection (ATP)은 악의적인 파일을 실수로 공유 하지 않도록 조직을 보호 합니다.

1. [보안 & 준수 센터로](https://protection.office.com) 이동 하 여 전역 관리자 계정으로 로그인 합니다.

2. 왼쪽 탐색 창의 **위협 관리**에서 **정책을**클릭 하 고 **ATP 안전한 첨부 파일**을 클릭 합니다. 

3. **SharePoint, OneDrive 및 Microsoft 팀의 파일을 보호**합니다. **SharePoint, OneDrive 및 Microsoft 팀에 대해 ATP 사용**을 선택 합니다.

4. **저장**을 클릭합니다.


### <a name="enable-anti-malware"></a>맬웨어 방지 사용

맬웨어는 바이러스 및 스파이웨어로 구성됩니다. 바이러스는 다른 프로그램 및 데이터를 감염시키며 컴퓨터 전체로 전파되어 감염시킬 프로그램을 찾습니다. 스파이웨어는 로그인 정보와 개인 데이터 등의 개인 정보를 수집하여 이를 맬웨어 작성자에게 보내는 맬웨어입니다. 

Microsoft 365에는 악성 소프트웨어 로부터 인바운드 및 아웃 바운드 메시지를 보호 하 고 스팸을 보호 하는 데 도움이 되는 맬웨어 및 스팸 필터링 기능이 기본적으로 제공 됩니다. 자세한 내용은 [스팸 방지 & 맬웨어 방지 보호](../security/office-365-security/anti-spam-and-anti-malware-protection.md)기능을 참조 하십시오.

일반적인 첨부 파일 형식이 포함 된 파일에서 맬웨어 방지 처리가 수행 되 고 있는지 확인 하려면 다음과 같이 합니다.

1. 브라우저에서 뒤로 단추를 클릭 하 여 **정책** 페이지로 돌아갑니다.
2. **맬웨어 방지**를 클릭 합니다.
3. **Default**라는 정책을 두 번 클릭 합니다.
4. **맬웨어 방지 정책** 창에서 **설정을**클릭 합니다.
4. **일반 첨부 파일 형식 필터**에서 **설정**를 선택 하 고 **저장**을 클릭 합니다.


## <a name="phase-3-examine-the-security-dashboard"></a>3 단계: 보안 대시보드 검사

Microsoft 365의 위협 관리 기능을 사용 하면 조직의 데이터에 대 한 모바일 장치 액세스를 제어 및 관리 하 고, 데이터 손실 로부터 조직을 보호 하 고, 악성 소프트웨어 및 스팸 으로부터 인바운드 및 아웃 바운드 메시지를 보호 하는 데 도움을 얻을 수 있습니다. 또한 위협 관리를 사용 하 여 도메인의 신뢰도를 보호 하 고 보낸 사람이 도메인에서 악의적으로 계정을 위장 하는지 여부를 확인 합니다. 

보안 대시보드를 보려면:

1. 필요한 경우 [보안 & 준수 센터로](https://protection.office.com) 이동 하 여 전역 관리자 계정으로 로그인 합니다.

2. 왼쪽 탐색 창의 **위협 관리**에서 **대시보드**를 클릭 합니다.

대시보드의 모든 카드를 살펴보고 제공 된 정보를 숙지 합니다.

자세한 내용은 [보안 대시보드](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard)를 참조 하세요.


## <a name="phase-4-examine-microsoft-secure-score"></a>4 단계: Microsoft 보안 점수 조사

Microsoft 보안 점수는 구독에서 사용할 수 있는 기능을 기준으로 현재 수준을 나타내는 숫자로, 보안 상황을 표시 합니다. 또한 점수를 높이기 위해 수행할 수 있는 개선 작업 목록을 제공 합니다.

1. 브라우저에서 새 탭을 만들고 [Microsoft 365 보안 센터로](https://security.microsoft.com/)이동한 후 **보안 점수**를 클릭 합니다.
2. **개요** 탭에서 현재 보안 점수를 확인 하 고, 유사한 라이선스 수를 포함 하는 전역 평균과 구독과 비교 하는 방법을 알아봅니다.
3. **향상 작업** 탭에서 점수를 증가 시키기 위해 수행할 수 있는 작업 목록을 읽습니다.

자세한 내용은 [Microsoft 보안 점수](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)를 참조 하세요.

## <a name="next-steps"></a>다음 단계

테스트 환경에서 추가 [정보 보호](m365-enterprise-test-lab-guides.md#information-protection) 기능에 대해 알아봅니다.

## <a name="see-also"></a>참고 항목

[엔터프라이증용 Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[엔터프라이즈 설명서에 대 한 Microsoft 365](https://docs.microsoft.com/microsoft-365-enterprise/)
