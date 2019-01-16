---
title: Microsoft 365 Enterprise 테스트 환경에 대한 Office 365 보안 강화
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Microsoft 365 Enterprise 테스트 환경을 추가 Office 365 보안 설정을 사용 하도록 설정 하려면이 테스트 랩 가이드를 사용 합니다.
ms.openlocfilehash: 62cf2347d3e003e9368c987912e7748029241501
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869986"
---
# <a name="increased-office-365-security-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise 테스트 환경에 대한 Office 365 보안 강화

이 문서의 지침을 함께 Microsoft 365 기업 테스트 환경에서 보안을 강화 하기 추가 Office 365 설정을 구성할 수 있습니다.

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>1 단계: Microsoft 365 Enterprise 테스트 환경을 구축합니다

최소 요구 사항을 경량 방식으로 Office 365 보안 강화를 구성 하려면 [경량 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지시를 따릅니다.
  
시뮬레이션 된 엔터프라이즈에서 Office 365 보안 강화 구성 하려는 경우 [통과 인증](pass-through-auth-m365-ent-test-environment.md)에 대 한 지침을 따릅니다.
  
> [!NOTE]
> Office 365 보안 강화를 테스트 하지 않아도 인터넷에 연결 하는 시뮬레이션 된 인트라넷을 포함 하는 시뮬레이션 된 엔터프라이즈 테스트 환경 및 Windows Server AD 포리스트에 대 한 디렉터리 동기화 합니다. 제공는 자동화 된 라이선스 및 그룹 구성원 자격을 테스트 하 고 일반적인 조직을 대표 하는 환경에서 사용해 수 있도록 하는 옵션으로 여기 합니다. 


## <a name="phase-2-configure-increased-office-365-security"></a>2 단계: Office 365 보안 강화 구성

이 단계에서 Microsoft 365 기업 테스트 환경에 대 한 Office 365 보안 강화를 사용 합니다. 추가 세부 정보 및 설정에 대 한 [구성을 보안 향상된을 위해 Office 365 테 넌 트](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)를 참조 하십시오.

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>SharePoint Online 현대 인증을 지원 하지 않는 응용 프로그램을 차단 하도록 구성

현대 인증을 지원 하지 않는 응용 프로그램 [id 및 장치에 대 한 액세스 구성](microsoft-365-policies-configurations.md) , 적용 된 Microsoft 365 구독 및 해당 디지털 자산을 보호의 중요 한 요소가 사용할 수 없습니다. 

1. Office 포털에 이동 ([https://office.com](https://office.com)) 전역 관리자 계정 사용 하 여 Office 365 평가판 구독에 로그인 합니다.
    
  - 로컬 컴퓨터에서 간단한 Microsoft 365 테스트 환경을 사용 하는 경우에 로그인 합니다.
    
  - 시뮬레이션 된 엔터프라이즈 Microsoft 365 테스트 환경을 사용 하는 경우 [Azure 포털](https://portal.azure.com) 을 사용 하 여 CLIENT1 가상 컴퓨터에 연결한 다음 CLIENT1에서 로그인 합니다.
 
2. **Microsoft 365 관리 센터** 탭에서 **관리**를 클릭 합니다.
3. 새 **Microsoft 365 관리 센터** 탭을 클릭 **관리 센터 > SharePoint**합니다.
4. 새 **SharePoint 관리 센터** 탭에서 **액세스 제어**를 클릭 합니다.
5. **현대 인증을 지원 하지 않는 하는 응용 프로그램** **블록**클릭 한 다음 **확인**을 클릭 합니다.


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>위협 보호 고급 사용 불가능) 개발자를 위한 SharePoint, 비즈니스 및 Microsoft 팀의 비즈니스용 OneDrive

Office 365 고급 위협 보호 (ATP) 기능의 Exchange Online Protection EOP ()는 데 도움이 되는 전자 메일에서 맬웨어를 유지 됩니다. ATP, Exchange 관리 센터 (EAC) 또는 보안 정책을 만들 & 사용자에 게 확인 하는 데 도움이 되는 준수 센터 링크 또는 하지 악의적으로 식별 되는 전자 메일에서 첨부 파일에 액세스 합니다. 자세한 내용은 [안전한 첨부 파일 및 안전 링크에 대 한 고급 위협 보호](https://docs.microsoft.com/office365/securitycompliance/office-365-atp)를 참조 하십시오.

1. 브라우저의 **Microsoft 365 관리 센터** 탭을 클릭 **관리 센터 > 보안 및 규정 준수**합니다.
2. 새 **보안 및 규정 준수** 탭을 클릭 **위협 관리 > 정책**합니다.
3. **ATP 안전한 첨부 파일**을 클릭 합니다.
4. **안전한 첨부 파일** 창에서 **SharePoint, OneDrive 및 Microsoft 팀의 ATP 설정**, 선택한 다음 **저장**을 클릭 합니다.

### <a name="enable-anti-malware"></a>맬웨어 방지를 사용 하도록 설정

맬웨어는 바이러스 및 스파이웨어로 구성 됩니다. 다른 프로그램 및 데이터, 바이러스 감염 및 감염 프로그램에 대 한 자세한 내용은 컴퓨터 전체로 확산 되기 합니다. 스파이웨어 로그인 정보 및 개인 데이터와 같은 개인 정보를 수집 하 고 해당 맬웨어 작성자에 게 다시 전송 하는 맬웨어를 가리킵니다. 

Office 365에 기본 제공 맬웨어 및 스팸 필터링 악성 소프트웨어에서 인바운드 및 아웃 바운드 메시지를 보호 하 고 스팸에서 사용자를 보호 하는 기능에 있습니다. 자세한 내용은 [Office 365의 스팸 방지 및 맬웨어 방지 보호 기능](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection) 을 참조 하십시오.

맬웨어 방지 처리 일반적인 첨부 파일 형식이 포함 된 파일에 대해 수행 되는 확인 합니다.

1. **정책** 페이지에는을 얻으려는 브라우저에서 뒤로 단추를 클릭 합니다.
2. **맬웨어 방지**를 클릭 합니다.
3. 라는 **기본**정책을 두번클릭 합니다.
4. **맬웨어 방지 정책** 창에서 **설정**을 클릭 합니다.
4. **일반 첨부 파일 형식 필터**클릭 **에 > 저장**합니다.


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a>3 단계: Office 365 보안 도구 및 로그를 검사 합니다.

이 단계는 보안 이벤트에 대 한 알리고 전반적인 보안 환경의 측정 하는 기본 제공 서비스에서 찾습니다.

### <a name="threat-management-dashboard"></a>위협 관리 대시보드

Office 365 위협 관리 제어 및 조직의 데이터에 대 한 모바일 장치 액세스를 관리 하 고, 조직에서 데이터 손실 보호 하 고 악성 소프트웨어와 스팸에서 인바운드 및 아웃 바운드 메시지를 보호할 수 있습니다. 또한 관리 하려면 도메인의 신뢰도 보호 하기 위해 및 보낸사람은 악의적으로 스푸핑 여부를 확인 하려면 도메인에서 계정을 위협을 사용 합니다. 자세한 내용은 [Office 365 보안 및 규정 준수 센터의 위협 관리](https://docs.microsoft.com/office365/securitycompliance/threat-management)를 참조 하십시오.

다음이 단계를 사용 하 여 Office 365 위협 관리 대시보드를 볼 수 있습니다.

1. 브라우저의 **Microsoft 365 관리 센터** 탭을 클릭 **관리 센터 > 보안 및 규정 준수**합니다.
2. 새 **보안 및 규정 준수** 탭을 클릭 **관리 위협 > 대시보드**합니다.
3. 브라우저에서 새 **대시보드** 탭에서 맬웨어 추세, 통찰력, 및 대시보드의 다른 섹션을 note 합니다.

### <a name="office-365-cloud-app-security-dashboard"></a>Office 365 클라우드 응용 프로그램 보안 대시보드

이전에 Office 365 고급 보안 관리 라고 office 365 클라우드 응용 프로그램 보안에 대 한 모니터링 하 고 알리기 위해 Office 365 구독에 의심 스러운 활동의 조사 하 고 가능한 수행할 수 있도록 하는 정책을 만들 수 있습니다. 업데이트 관리 작업입니다. 자세한 내용은 [개요 (영문)의 Office 365 클라우드 응용 프로그램 보안](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview)을 참조 하십시오.

1. 브라우저의 **Microsoft 365 관리 센터** 탭을 클릭 **관리 센터 > 보안 및 규정 준수**합니다.
2. 새 **보안 및 규정 준수** 탭을 클릭 **알림 > 고급 알림 관리 > Office 365 클라우드 응용 프로그램 보안으로 이동**합니다.
3. 새로운 **클라우드 앱 보안** 탭에서 대시보드 보기 및 Office 365 구독에서 다양 한 활동에 대 한 모니터링 하는 기본 정책 목록 note 합니다.
4. 추적 하는 클라우드 응용 프로그램 보안 활동의 요약을 보려면 대시보드 아이콘을 클릭 합니다.
5. **조사** (안경 아이콘) 및 **작업 로그** 최근 로그인의 목록 및 기타 활동을 참조 하려면 다음을 클릭 합니다.

### <a name="secure-score"></a>보안 점수

1. 브라우저에서 새 탭을 만들고 **securescore.office.com**로 이동 합니다.
2. **대시보드 탭**현재 보안 점수가 및 큐의 작업 목록이 점수 향상 note 합니다.

정보 및 프로덕션 환경에서 이러한 설정을 구성 하는 링크에 대 한 **정보 보호** 단계에서 [Configure Office 365에 대 한 보안을 향상](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) 하는 단계를 참조 하십시오.

## <a name="next-step"></a>다음 단계

추가 [정보 보호](m365-enterprise-test-lab-guides.md#information-protection) 기능 및 기능 테스트 환경에서 살펴봅니다.

## <a name="see-also"></a>참고 항목

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise 배포](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)

