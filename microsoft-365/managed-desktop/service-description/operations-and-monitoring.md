---
title: Microsoft Managed Desktop 작업 및 모니터링
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: c618c5bf2acf50d84aca354975670ed84b581601
ms.sourcegitcommit: 0dde96d5864e5b16ea24cfb302930b041c7a8091
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "34431919"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft Managed Desktop 작업 및 모니터링

<!-- Operations and monitoring: -->


## <a name="change-management"></a>변경 관리

서비스 제공에서 하드웨어 유지 관리 및 보안 업데이트와 같은 작업에 대한 책임의 균형이 고객이 아닌 서비스 공급자(Microsoft)에게 이동됩니다. 그러나 업데이트를 롤아웃할 때 타사 및 사용자 지정 소프트웨어가 계속 예상 대로 작동 하는지 확인 해야 합니다.

온-프레미스 제품의 경우 조직에서는 변경 관리에 대 한 모든 책임을 가정 합니다.

### <a name="balance-of-responsibility"></a>책임의 균형

책임 | Microsoft Managed Desktop 서비스 | Microsoft 365 클라이언트 소프트웨어 | 온-프레미스 클라이언트 및 서버 | 타사 및 사용자 지정 소프트웨어
----- | ----- | ----- | ----- | -----
새로운 기능 제공 | Microsoft | Microsoft | 모두 | 고객
품질 보증에 위해 새로운 기능 테스트 |  Microsoft | Microsoft | 모두 | 고객
새로운 기능에 대한 소식 전달 | 모두 | 모두 | 모두 | 고객
사용자 지정 소프트웨어 통합 | 모두 | 모두 | 고객 | 고객
보안 업데이트 적용 | Microsoft | Microsoft | 고객 | 고객
시스템 소프트웨어 유지 관리 | Microsoft | Microsoft | 고객 | 고객
배포용 패키지 | Microsoft | Microsoft | 고객 | 고객


### <a name="change-process-overview"></a>변경 프로세스 개요

다음은 Microsoft와 고객 간에 변경 프로세스를 공유 하는 방법을 요약 한 것입니다. 



<table>
<tr><th></th><th><p>Microsoft의 역할:</p></th><th><p>고객의 역할:</p></th></tr>
<tr><td>변경 전</td><td><ul><li>서비스 변경에 대한 기대 수준을 설정합니다.</li><li>관리자 작업을 수행 해야 하는 변경 내용을 사용자에 게 5 일 전에 고객에 게 알립니다.</li><li>응급 변경 사항에 대해 알리기 전에 완화를 적용 합니다.</li></ul></td><td><ul><li>변경 및 통신에 대한 예상 결과를 이해합니다.</li><li>정기적으로 Microsoft Managed Desktop 메시지 센터를 읽습니다.</li><li>내부 변경 관리 프로세스를 검토하고 업데이트합니다.</li><li>Microsoft Managed Desktop 요구 사항을 이해 하 고 준수 하는지 확인 합니다. </li><li>승인 및 승인 (필요한 경우)</li></ul></td></tr><tr><td>변경 도중</td><td><ul><li>Windows 10 및 Office 365 클라이언트에 대 한 월별 보안 및 비보안 업데이트를 릴리스 및 배포 합니다.</li><li>데이터 신호를 모니터링 하 고 영향을 주는 큐를 지원 합니다.</li></ul></td><td><ul><li>Microsoft Managed Desktop 메시지 센터를 확인 하 고 추가 정보를 검토 합니다.</li><li>   해당 하는 경우 필요한 작업을 수행 하 고 응용 프로그램을 테스트 합니다.</li><li>중단/수정 시나리오가 발생 하는 경우 지원 요청을 만듭니다.</li></ul></td></tr><tr><td>변경 후</td><td><ul><li>고객 의견을 수집 하 여 향후 변경 사항에 대 한 롤아웃을 개선 합니다.</li><li>데이터 신호를 모니터링 하 고 영향을 주는 큐를 지원 합니다.</li></ul></td><td><ul><li>조직 내 사용자와 협력 하 여 변경을 채택 합니다.</li><li>   영업 기회에 대 한 변경 및 채택 관리 프로세스를 검토 하 여 효율성을 확보 합니다.</li><li>관리자 의견 도구에 일반적인 의견 및 구체적인 의견을 제공 합니다.</li><li>Office 앱에서 Windows 피드백 허브 및 웃는 얼굴 단추를 사용 하 여 앱 관련 피드백을 제공 하도록 사용자를 교육 합니다.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>변경 유형

서비스에 대해 정기적으로 수행 되는 몇 가지 유형의 변경 사항이 있습니다. 이러한 변경 및 고객이 담당 하는 작업에 대 한 통신 채널은 다양 합니다.

모든 변경 내용이 사용자에게 동일한 영향을 미치는 것은 아니며 필요한 작업도 다를 수 있습니다. 일부는 계획 되 고 일부 계획 되지 않은 경우 (대개 비보안 업데이트 및 보안 업데이트가 계획 되지 않음) 변경 유형에 따라 통신 채널이 다를 수 있습니다. 다음 표에는 Microsoft Managed Desktop service에 대해 예상 되는 변경 유형이 나와 있습니다.

|   | 동작 |   비보안 업데이트 |  보안
--- | --- | --- | ---
**변경 유형** | 기능 업데이트<br>-새로운 기능 또는 응용 프로그램<br>-더 이상 사용 되지 않는 기능 | 문제에 대한 클라이언트 핫픽스 | 보안 패치
**사전 알림** | 작업이 필요한 변경 내용에 대 한 5 일 유의 사항 |    아니요, 월별 릴리스에 포함 되어 있습니다.   | 아니요, 월별 릴리스에 포함 되어 있습니다. 
**통신 채널** | -메시지 센터<br>-전자 메일 경고 | -메시지 센터<br>-전자 메일 경고 | -메시지 센터<br>-전자 메일 경고
**테 넌 트 관리 작업 필요** | 가끔 |  거의 필요 없음 |    거의 필요 없음 
**작업 유형** | 설정 변경 | 사용자에게 변경 내용 전달 | 관리 설정 변경     
**테스트 필요** | 원격 액세스 서비스를 포함 하 여 비즈니스 응용 프로그램 확인 |  가끔 - 프로세스 또는 사용자 지정 내용에 대해 수정 프로그램 테스트 |   거의 필요 없음 
**변경 예** | -기능 업데이트: IT 관리 포털 간소화 된 지원 티켓 제출 및 검토<br>-새로운 기능 또는 응용 프로그램: Windows 10 기능 업데이트의 반기 릴리스 | 고객이 보고한 버그에 따른 핫픽스 |  


## <a name="standard-operating-procedures"></a>표준 운영 절차

Microsoft 관리 데스크톱 서비스는 microsoft 클라우드 인스턴스에서 다른 관리 작업을 수행할 수 있는 microsoft에서 구현 되 고 운영 됩니다. Microsoft는 Microsoft Managed Desktop 관련 설치, 구성 및 운영에만 책임이 있습니다. 

온-프레미스 제품의 경우 조직에서 설치 및 구성 및 운영 작업을 관리 하는 모든 책임을 맡습니다.

범주 |    Microsoft는 | 고객은
--- | --- | ---
네트워크 (프록시, 패킷 검사, VPN)  | 비즈니스 사용자에 대 한 위험을 최소화 하는 고객을 권고 하 고 계획 합니다. | -Microsoft에서 검토할 수 있는 구성 세부 정보, 범위, 시간 표시 막대 및 기타 관련 세부 정보를 비롯 하 여 계획 된 구성 변경에 대 한 정보를 요청 하는 지원 요청을 만듭니다.<br>-Microsoft Managed Desktop Operations가 평가 되 고 advise 된 경우에만 변경 내용을 적용 합니다.
서비스 계정 |-자격 증명을 구현 하 고 안전 하 게 저장 하 고 관리 합니다.<br> -보안 운영 팀에 이러한 자격 증명을 무단으로 액세스 하거나 사용 하지 못하도록 합니다. | -Microsoft에서 검토할 수 있는 구성 세부 정보, 범위, 시간 표시 막대 및 기타 관련 세부 정보를 비롯 하 여 계획 된 구성 변경에 대 한 정보를 요청 하는 지원 요청을 만듭니다.<br>-Microsoft Managed Desktop Operations가 평가 되 고 advise 된 경우에만 변경 내용을 적용 합니다.<br>-정책, 다단계 인증, 조건부 액세스 또는 Microsoft Managed Desktop Service 계정에 응용 프로그램 배포를 할당 하지 않습니다.<br>-암호를 다시 설정 하거나 자격 증명을 사용 하지 않습니다.<br>-이 서비스 계정과 관련 된 Intune 또는 Azure 감사 로그에서 의심 스러운 작업이 관찰 되는 경우 Microsoft Managed Desktop 작업에 대 한 Sev C 지원 요청을 엽니다.
장치 그룹 | -Microsoft 관리 되는 데스크톱 그룹 내에서 장치의 구성원을 구현 하 고 관리 합니다.<br>-Microsoft 관리 데스크톱 그룹을 사용 하 여 구성 및 장치에 대 한 업데이트 및 구성을 관리 합니다. | -Microsoft에서 검토할 수 있는 구성 세부 정보, 범위, 시간 표시 막대 및 기타 관련 세부 정보를 비롯 하 여 계획 된 구성 변경에 대 한 정보를 요청 하는 지원 요청을 만듭니다.<br>-Microsoft Managed Desktop Operations가 평가 되 고 advise 된 경우에만 변경 내용을 적용 합니다.<br>-Microsoft 관리 되는 데스크톱 그룹의 구성원 자격을 수정 하지 않습니다.<br>-그룹을 사용 하 여 VPN, Windows Hello 또는 전자 메일 암호화 또는 회사 Wi-fi 프로필 구성 같은 서비스에 대해 회사 인증서를 할당 합니다.<br>-공동 관리가 있는 경우 Configuration Manager 클라이언트를 배포할 때 모든 Microsoft 관리 되는 데스크톱 그룹을 명시적으로 제외 합니다.
정책도 |  -서비스 내의 장치 구성 상태를 제어 하는 Microsoft Managed Desktop 정책을 구현 하 고 관리 합니다.<br>-장치 그룹을 점진적으로 사용 하 여 정책 또는 Windows에 업데이트를 배포 합니다.<br> -Microsoft에서 관리 하지 않는 대상 데스크톱 그룹을 명시적으로 제외 합니다. | -Microsoft에서 검토할 수 있는 구성 세부 정보, 범위, 시간 표시 막대 및 기타 관련 세부 정보를 비롯 하 여 계획 된 구성 변경에 대 한 정보를 요청 하는 지원 요청을 만듭니다.<br>-Microsoft Managed Desktop Operations가 평가 되 고 advise 된 경우에만 변경 내용을 적용 합니다.<br>-Microsoft managed desktop service를 통해 관리 되지 않는 장치나 사용자에 게 Microsoft 관리 데스크톱 정책을 편집 하거나 할당 하지 않습니다.
Windows Defender Advanced Threat Protection | Microsoft Managed Desktop service의 범위 내에서 장치를 모니터링 하 고 조사 합니다. | -Microsoft에서 검토할 수 있는 구성 세부 정보, 범위, 시간 표시 막대 및 기타 관련 세부 정보를 비롯 하 여 계획 된 구성 변경에 대 한 정보를 요청 하는 지원 요청을 만듭니다.<br>-Microsoft Managed Desktop Operations가 평가 되 고 권장 되는 경우 변경 내용을 적용 합니다.
비즈니스용 Microsoft Store |  Microsoft Managed Desktop service에 대 한 Windows Autopilot 프로필을 구성 하 고 유지 관리 합니다. | -Microsoft에서 검토할 수 있는 구성 세부 정보, 범위, 시간 표시 막대 및 기타 관련 세부 정보를 비롯 하 여 계획 된 구성 변경에 대 한 정보를 요청 하는 지원 요청을 만듭니다.<br>-Microsoft Managed Desktop Operations가 평가 되 고 advise 된 경우에만 변경 내용을 적용 합니다.<br>-Microsoft Managed Desktop Windows Autopilot profile의 구성을 수정 하지 않거나 할당 된 장치를 추가/제거 합니다.
인증서 | | -Microsoft에서 검토할 수 있는 구성 세부 정보, 범위, 시간 표시 막대 및 기타 관련 세부 정보를 비롯 하 여, 인증서가 만료 되기 전에 60 일 이내에 지원 요청을 만들어 계획 된 구성 변경을 요청 합니다.<br>-Microsoft Managed Desktop Operations가 평가 되 고 advise 된 경우에만 변경 내용을 적용 합니다.<br>-인증서 프로필, VPN 프로필 및 Wi-fi 프로필을 구성 하는 데 필요한 모든 인증서를 업데이트 합니다.




## <a name="device-wipe-with-factory-reset"></a>공장 초기화로 장치 지우기

관리 되는 데스크톱 운영 팀에서는 reimaged 해야 하는 Microsoft Managed Desktop 관리 장치에 대해 팩터리를 다시 설정할 수 있습니다. 이 기능은 다른 직원에 게 장치를 제공 해야 하거나 직원이 회사를 떠나는 경우에 유용 합니다. 

다음과 같은 몇 가지 요구 사항이 있습니다.

- 고객의 테 넌 트 관리자가 서비스 요청을 제출 해야 합니다.
- 장치에 대 한 컴퓨터 이름이 필요 합니다.
- 초기화를 수행 하기 전에 사용자 계정이 Azure AD에 있어야 합니다.

관리 데스크톱 운영 팀은 다음을 수행 합니다.

- Intune에서 장치 이름 조회
- 장치에 공장 리셋 명령 보내기

>[!NOTE]
>공장 초기화를 수행 하기 전에 Azure AD에서 사용자 계정을 제거 하지 마십시오. 사용자가 Azure AD에 없는 경우 Intune이 장치에 공장 리셋 명령을 보낼 수 없습니다. 

장치가 OOBE로 부팅 되 고 미리 설치 된 모든 응용 프로그램 및 설정이 다시 적용 됩니다. 장치 사용자는 초기 설정 정보를 다시 제공 해야 합니다. 

장치를 다시 설정한 경우 조직의 다른 사람에 게 제공할 수 있습니다. 이전 사용자의 데이터 또는 enterprise 데이터는 장치에 표시 되지 않습니다. 다음 사용자는 이전 사용자가 새로운 Microsoft Managed Desktop 장치와 동일한 프로세스를 진행 합니다.

이 프로세스에서 BitLocker는 데이터 보안의 주요 구성 요소입니다. Microsoft Managed 데스크톱 장치에 대 한 BitLocker 암호화를 사용 하면 초기화가 장치에 적용 된 후에도 드라이브의 데이터가 안전 하 게 유지 됩니다. 드라이브에 있던 모든 데이터는 장치의 다음 사용자가 사용할 수 없게 됩니다. 자세한 내용은 [BitLocker overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)를 참조 하세요.

자세한 내용은 [공장 초기화 장치를](https://docs.microsoft.com/intune/devices-wipe#factory-reset-a-device)참조 하세요. 
