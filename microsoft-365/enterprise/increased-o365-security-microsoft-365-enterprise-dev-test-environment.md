---
title: 엔터프라이즈 Microsoft 365 환경의 Microsoft 365 보안 강화
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection: M365-security-compliance
ms.custom:
- Ent_TLGs
- admindeeplinkMAC
- admindeeplinkDEFENDER
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 이 테스트 랩 가이드를 사용하여 엔터프라이즈 테스트 환경에 Microsoft 365 추가 보안 Microsoft 365 사용하도록 설정할 수 있습니다.
ms.openlocfilehash: 3976ad11b6cac7ae74e0fd2d94ad35b610273052
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2021
ms.locfileid: "60960865"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a>엔터프라이즈 Microsoft 365 환경의 Microsoft 365 보안 강화

*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경에 Microsoft 365 사용할 수 있습니다.*

이 문서의 지침에 따라 엔터프라이즈 테스트 환경의 보안 Microsoft 365 추가 Microsoft 365 구성합니다.

![Microsoft 클라우드용 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [여기](../downloads/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>1단계: 엔터프라이즈 테스트 Microsoft 365 사용자 환경 구축

최소 요구 사항과 Microsoft 365 경량 방식으로 강화된 보안만 구성하려면 [Lightweight base configuration의 지침을 따릅니다.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
시뮬레이트된 엔터프라이즈에서 Microsoft 365 보안 강화를 구성하려는 경우 통과 인증의 [지침을 따릅니다.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> 보안이 강화된 Microsoft 365 테스트 환경에는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요하지 않습니다. 여기에는 인터넷에 연결된 시뮬레이트된 인트라넷과 AD DS(Active Directory 도메인 서비스) 포리스트에 대한 디렉터리 동기화가 포함됩니다. 여기서는 옵션으로 제공되어 자동화된 라이선싱 및 그룹 멤버 자격을 테스트하고 일반적인 조직을 나타내는 환경에서 실험해 볼 수 있습니다. 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>2단계: 보안 강화 Microsoft 365 구성

이 단계에서는 엔터프라이즈 테스트 환경에 Microsoft 365 보안 강화를 Microsoft 365 수 있습니다. 자세한 내용 및 설정은 보안 강화를 [위해 테넌트 구성을 참조하세요.](/office365/securitycompliance/tenant-wide-setup-for-increased-security)

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>최신 SharePoint 지원하지 않는 앱을 차단하도록 SharePoint Online 구성

최신 인증을 지원하지 않는 [](../security/office-365-security/microsoft-365-policies-configurations.md) 앱에는 ID 및 장치 액세스 구성을 적용할 수 없습니다. 이는 Microsoft 365 디지털 자산을 보호하는 데 중요한 요소입니다. 

1. 사용자 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">계정으로 Microsoft 365 관리 센터</a> 전역 관리자 계정으로 Microsoft 365 테스트 랩 구독에 로그인합니다.
    
  - 간단한 테스트 환경을 사용하는 Microsoft 365 로컬 컴퓨터에서 로그인합니다.
    
  - 시뮬레이트된 엔터프라이즈 Microsoft 365 환경을 사용하는 경우 Azure [Portal을](https://portal.azure.com) 사용하여 CLIENT1 가상 컴퓨터에 연결한 다음 CLIENT1에서 로그인합니다.
 
2. 새 **Microsoft 365 관리 센터** 탭의 왼쪽 탐색  창의 관리 센터에서 를 **SharePoint.**
3. 새 SharePoint **관리** 센터 탭에서 액세스 제어 **> 클릭합니다.**
4. 최신 **인증을** 지원하지 않는 앱을 클릭하고 액세스 차단을 선택한 **다음** 저장을 **클릭합니다.**


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>사용자, Office 365 및 SharePoint 및 비즈니스용 OneDrive Defender를 사용하도록 Microsoft Teams

조직에서 Office 365, SharePoint OneDrive Microsoft Teams 파일을 공유하지 못하게 조직을 보호합니다.

1. 보안 및 준수 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">& 이동하고</a> 전역 관리자 계정으로 로그인합니다.

2. 왼쪽 탐색 창의 **위협** 관리에서 정책 을 **클릭한** 다음 첨부 **금고 클릭합니다.** 

3. 의 **파일 보호에서 SharePoint,** OneDrive 및 Microsoft Teams. 에 **대해 ATP 켜기, SharePoint,** OneDrive 및 Microsoft Teams.

4. **저장** 을 클릭합니다.


### <a name="enable-anti-malware"></a>맬웨어 방지 사용

맬웨어는 바이러스 및 스파이웨어로 구성됩니다. 바이러스는 다른 프로그램 및 데이터를 감염시키며 컴퓨터 전체로 전파되어 감염시킬 프로그램을 찾습니다. 스파이웨어는 로그인 정보와 개인 데이터 등의 개인 정보를 수집하여 이를 맬웨어 작성자에게 보내는 맬웨어입니다. 

Microsoft 365 맬웨어 및 스팸 필터링 기능이 내장되어 있으며 인바운드 및 아웃바운드 메시지를 악성 소프트웨어로부터 보호하고 스팸으로부터 보호하는 데 도움이 됩니다. 자세한 내용은 맬웨어 방지 [보호 & 스팸 방지를 참조하세요.](../security/office-365-security/anti-spam-and-anti-malware-protection.md)

일반적인 첨부 파일 형식의 파일에 대해 맬웨어 방지 처리가 수행되도록 보장하려면

1. 브라우저에서 뒤로 단추를 클릭하여 정책  페이지로 돌아오십시오.
2. **맬웨어 방지 를 클릭합니다.**
3. Default라는 정책을 두 번 **클릭합니다.**
4. **맬웨어 방지 정책** 창에서 를 **설정.**
4. 일반 첨부 파일 형식  **필터에서** 을 선택하고 저장을 **클릭합니다.**


## <a name="phase-3-examine-the-security-dashboard"></a>3단계: 보안 대시보드 검사

조직의 위협 Microsoft 365 관리하면 조직의 데이터에 대한 모바일 장치 액세스를 제어 및 관리하고, 데이터 손실로부터 조직을 보호하고, 악성 소프트웨어 및 스팸으로부터 인바운드 및 아웃바운드 메시지를 보호할 수 있습니다. 또한 위협 관리를 사용하여 도메인의 평판을 보호하고 보낸 사람이 도메인의 계정을 악의적으로 스푸핑하는지 여부를 확인할 수 있습니다. 

보안 대시보드를 표시하는 데 사용할 수 있는 내용은 다음을 참조하세요.

1. 필요한 경우 보안 및 준수 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">&</a> 이동하여 전역 관리자 계정으로 로그인합니다.

2. 왼쪽 탐색 창의 **위협** 관리에서 대시보드 를 **클릭합니다.**

대시보드의 모든 카드를 살펴보고 제공된 정보를 익히세요.

자세한 내용은 보안 [대시보드를 참조하세요.](../security/office-365-security/security-dashboard.md)


## <a name="phase-4-examine-microsoft-secure-score"></a>4단계: Microsoft 보안 점수 검사

Microsoft 보안 점수는 구독에서 사용할 수 있는 기능을 상대로 현재 수준을 나타내는 숫자로 보안 상태 표시 또한 점수를 개선하기 위해 수행할 수 있는 개선 작업 목록도 있습니다.

1. 브라우저에서 새 탭을 만들고 Microsoft 365 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">센터로</a>이동한 다음 보안 점수 **를 클릭합니다.**
2. 개요 **탭에서**  현재 보안 점수와 전역 평균 및 라이선스 수가 비슷한 구독과 비교하는 방법을 기록해 넣습니다.
3. 개선 **작업 탭에서** 점수를 높이기 위해 수행할 수 있는 작업 목록을 읽어 읽습니다.

자세한 내용은 Microsoft 보안 점수를 [참조하세요.](../security/defender/microsoft-secure-score.md)

## <a name="next-steps"></a>다음 단계

테스트 환경의 추가 [정보](m365-enterprise-test-lab-guides.md#information-protection) 보호 기능을 살펴보아야 합니다.

## <a name="see-also"></a>참고 항목

[엔터프라이증용 Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[기업용 Microsoft 365 설명서](/microsoft-365-enterprise/)