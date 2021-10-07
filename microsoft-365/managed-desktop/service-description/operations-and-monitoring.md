---
title: Microsoft Managed Desktop 작업 및 모니터링
description: Who 변경 프로세스에 대한 자세한
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 7a12a1304d562ae74d4d1e7e4e6d14a947934636
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197104"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft Managed Desktop 작업 및 모니터링

<!-- Operations and monitoring: -->

## <a name="change-management"></a>변경 관리

서비스 제공에서 하드웨어 유지 관리 및 보안 업데이트와 같은 작업에 대한 책임의 균형이 고객이 아닌 서비스 공급자(Microsoft)에게 이동됩니다. 그러나 업데이트가 롤아웃될 때 Microsoft가 아닌 소프트웨어와 사용자 지정 소프트웨어가 예상대로 계속 작동하도록 해야 합니다.

조직은 사내 제품의 경우 변경 관리에 대한 모든 책임을 하게 됩니다.

### <a name="balance-of-responsibility"></a>책임 균형

책임 | Microsoft Managed Desktop 서비스 | Microsoft 365 클라이언트 소프트웨어 | 온-프레미스 클라이언트 및 서버 | 비 Microsoft 및 사용자 지정 소프트웨어
----- | ----- | ----- | ----- | -----
새로운 기능 제공 | Microsoft | Microsoft | 둘 다 | 고객
품질 보증에 위해 새로운 기능 테스트 |  Microsoft | Microsoft | 둘 다 | 고객
새로운 기능에 대한 소식 전달 | 둘 다 | 둘 다 | 둘 다 | 고객
사용자 지정 소프트웨어 통합 | 둘 다 | 둘 다 | 고객 | 고객
보안 업데이트 적용 | Microsoft | Microsoft | 고객 | 고객
시스템 소프트웨어 유지 관리 | Microsoft | Microsoft | 고객 | 고객
배포용 패키지 | Microsoft | Microsoft | 고객 | 고객

### <a name="change-process-overview"></a>프로세스 개요 변경

Microsoft와 고객 간에 변경 프로세스를 공유하는 방법에 대한 요약은 다음과 같습니다. 

<table>
<tr><th></th><th><p>Microsoft의 역할:</p></th><th><p>고객의 역할:</p></th></tr>
<tr><td>변경 전</td><td><ul><li>서비스 변경에 대한 기대 수준을 설정합니다.</li><li>관리자 조치가 필요한 변경에 대해 5일 전에 고객에게 알립니다.</li><li>긴급 변경의 경우 알림 전에 완화를 적용합니다.</li></ul></td><td><ul><li>변경 및 통신에 대한 예상 결과를 이해합니다.</li><li>메시지 Microsoft Managed Desktop 읽기</li><li>내부 변경 관리 프로세스를 검토하고 업데이트합니다.</li><li>요구 사항을 이해하고 준수하는지 Microsoft Managed Desktop 확인합니다. </li><li>필요한 경우 승인 및 승인합니다.</li></ul></td></tr><tr><td>변경 도중</td><td><ul><li>Windows 10 클라이언트에 대한 월별 보안 및 비보안 Office 365 릴리스하고 배포합니다.</li><li>데이터 신호를 모니터링하고 영향을 미치는 큐를 지원합니다.</li></ul></td><td><ul><li>메시지 Microsoft Managed Desktop 확인한 후 추가 정보를 검토합니다.</li><li>해당하는 경우 필요한 작업을 수행하고 응용 프로그램을 테스트합니다.</li><li>중단/수정 시나리오가 있는 경우 지원 요청을 생성합니다.</li></ul></td></tr><tr><td>변경 후</td><td><ul><li>향후 변경 내용의 롤아웃을 개선하기 위해 고객 의견을 수집합니다.</li><li>데이터 신호를 모니터링하고 영향을 미치는 큐를 지원합니다.</li></ul></td><td><ul><li>조직의 사용자와 함께 변경을 채택합니다.</li><li>효율성을 얻기 위한 기회를 얻기 위한 변경 및 채택 관리 프로세스를 검토합니다.</li><li>관리자 피드백 도구에서 일반적인 피드백 및 특정 피드백을 제공합니다.</li><li>앱의 스마일 단추 및 스마일 단추를 사용하여 Windows 피드백 허브 피드백을 제공하도록 Office 교육합니다.</li></ul></td></tr>
<table> 

### <a name="change-types"></a>변경 유형

서비스를 정기적으로 변경하는 몇 가지 유형이 있습니다. 이러한 변경 내용에 대한 통신 채널과 책임이 있는 작업은 다양합니다.

모든 변경 내용이 사용자에게 동일한 영향을 미치는 것은 아니며 필요한 작업도 다를 수 있습니다. 일부는 계획된 것이고 일부 계획되지 않은 경우도 있습니다(비보안 업데이트 및 보안 업데이트는 일반적으로 계획되지 않습니다). 변경 유형에 따라 통신 채널이 다를 수 있습니다. 다음 표에는 서비스에서 사용할 수 있는 변경 유형이 Microsoft Managed Desktop 나열되어 있습니다.

|   | 기능 | 비보안 업데이트 | 보안
--- | --- | --- | ---
**변경 유형** | - 기능 업데이트<br>- 새로운 기능 또는 응용 프로그램<br>- 사용 불가능한 기능 | 문제에 대한 클라이언트 핫픽스 | 보안 업데이트
**사전 알림** | 작업이 필요한 변경 내용에 대한 5일 알림 | 아니요. 이러한 변경 내용은 월별 릴리스에 포함됩니다. | 아니요. 변경 내용이 월별 릴리스에 포함됩니다. 
**통신 채널** | - 메시지 센터<br>- 전자 메일 알림 | - 메시지 센터<br>- 전자 메일 알림 | - 메시지 센터<br>- 전자 메일 알림
**전역 관리자 작업이 필요합니다.** | 가끔 | 거의 필요 없음 | 거의 필요 없음 
**작업 유형** | 설정 변경 | 사용자에게 변경 내용 전달 | 관리 설정 변경  
**테스트 필요** | 원격 액세스 서비스를 비롯한 비즈니스 응용 프로그램 확인 | 가끔 - 프로세스 또는 사용자 지정 내용에 대해 수정 프로그램 테스트 | 거의 필요 없음 
**변경 예** | - 기능 업데이트: IT 관리 포털 지원 티켓 제출 및 검토 간소화<br>- 새로운 기능 또는 응용 프로그램: Semi-Annual 업데이트의 Windows 10 릴리스 | 고객이 보고한 버그에 따른 핫픽스 |

## <a name="standard-operating-procedures"></a>표준 운영 절차

Microsoft Managed Desktop 서비스는 Microsoft에서 다른 관리 활동을 수행 할 수 있는 Microsoft 클라우드 인스턴스에서 구현 및 운영됩니다. Microsoft는 특정 설정, Microsoft Managed Desktop 및 운영에 전적으로 책임을 져야 합니다.

사내 제품의 경우 조직은 설치 관리와 구성 및 운영 활동을 관리하는 모든 책임을 집니다.

Categories | Microsoft는 | 고객은
--- | --- | ---
네트워크(프록시, 패킷 검사, VPN)  | 비즈니스 사용자에 대한 위험을 최소화하도록 고객과의 조언 및 계획 | - Microsoft에서 검토할 구성 세부 정보, 범위, 타임라인 및 기타 관련 세부 정보를 포함하여 계획된 구성 변경에 대한 요청 정보를 요청하는 지원 요청 정보를 만들 수 있습니다.<br>- Operations가 평가 및 Microsoft Managed Desktop 한 번만 변경을 적용합니다.
서비스 계정 |- 자격 증명을 구현, 안전하게 저장 및 관리합니다.<br> - 이러한 자격 증명의 무단 액세스 또는 사용을 보안 운영 팀에 전달합니다. | - Microsoft에서 검토할 구성 세부 정보, 범위, 타임라인 및 기타 관련 세부 정보를 포함하여 계획된 구성 변경에 대한 요청 정보를 요청하는 지원 요청 정보를 만들 수 있습니다.<br>- Operations가 평가 및 Microsoft Managed Desktop 한 번만 변경을 적용합니다.<br>- 서비스 계정에 정책, 다단계 인증, 조건부 액세스 또는 응용 프로그램 배포를 Microsoft Managed Desktop 않습니다.<br>- 암호를 다시 설정하거나 자격 증명을 사용하지 않습니다.<br>- Intune 또는 Azure 감사 로그에서 의심스러운 활동이 관찰된 경우 이러한 서비스 계정과 관련된 Microsoft Managed Desktop Operations에 대한 Sev C 지원 요청을 하세요.
장치 그룹 | - 그룹 내에서 디바이스의 멤버 자격을 구현하고 Microsoft Managed Desktop.<br>- Microsoft Managed Desktop 그룹을 사용하여 디바이스에 대한 구성 및 업데이트의 할당 및 릴리스를 관리합니다. | - Microsoft에서 검토할 구성 세부 정보, 범위, 타임라인 및 기타 관련 세부 정보를 포함하여 계획된 구성 변경에 대한 요청 정보를 요청하는 지원 요청 정보를 만들 수 있습니다.<br>- Operations가 평가 및 Microsoft Managed Desktop 한 번만 변경을 적용합니다.<br>- 배포 그룹에 장치 Microsoft Managed Desktop 단계에 따라 모든 Microsoft Managed Desktop 그룹에만 장치를 [할당합니다.](../working-with-managed-desktop/assign-deployment-group.md)<br>- VPN, 비즈니스용 또는 전자 메일 암호화 또는 회사 wifi 프로필 Windows Hello 서비스에 대한 회사 인증서를 할당하려면 그룹만 사용합니다.<br>- 공동 관리가 있는 경우 Configuration Manager 클라이언트를 배포할 Microsoft Managed Desktop 모든 사용자 그룹을 명시적으로 제외합니다.
정책 | - 서비스 내의 장치 구성 상태를 Microsoft Managed Desktop 정책을 구현하고 관리합니다.<br>- 장치 그룹을 사용하여 Windows 또는 정책에 업데이트를 배포합니다.<br> - 비영리 그룹 대상 지정을 Microsoft Managed Desktop 명시적으로 제외 | - Microsoft에서 검토할 구성 세부 정보, 범위, 타임라인 및 기타 관련 세부 정보를 포함하여 계획된 구성 변경에 대한 요청 정보를 요청하는 지원 요청 정보를 만들 수 있습니다.<br>- Operations가 평가 및 Microsoft Managed Desktop 한 번만 변경을 적용합니다.<br>- Microsoft Managed Desktop 서비스에서 관리하지 않는 장치 또는 사용자에게 Microsoft Managed Desktop 할당하지 않습니다.
엔드포인트용 Microsoft Defender | Microsoft Managed Desktop 서비스 범위 내의 장치를 모니터링하고 조사합니다. | - Microsoft에서 검토할 구성 세부 정보, 범위, 타임라인 및 기타 관련 세부 정보를 포함하여 계획된 구성 변경에 대한 요청 정보를 요청하는 지원 요청 정보를 만들 수 있습니다.<br>- Operations가 평가 및 Microsoft Managed Desktop 한 번만 변경 적용
비즈니스용 Microsoft Store | Windows 서비스에 대한 Autopilot 프로필을 구성하고 Microsoft Managed Desktop 유지 관리합니다. | - Microsoft에서 검토할 구성 세부 정보, 범위, 타임라인 및 기타 관련 세부 정보를 포함하여 계획된 구성 변경에 대한 요청 정보를 요청하는 지원 요청 정보를 만들 수 있습니다.<br>- Operations가 평가 및 Microsoft Managed Desktop 한 번만 변경을 적용합니다.<br>- Autopilot 프로필의 구성을 Microsoft Managed Desktop Windows 할당된 디바이스를 추가/제거하지 않습니다.
인증서 | | - 인증서 만료 60일 전에 지원 요청을 만들고 구성 세부 정보, 범위, 타임라인 및 Microsoft가 검토할 기타 관련 세부 정보를 포함하여 계획된 구성 변경에 대한 정보를 요청합니다.<br>- Operations가 평가 및 Microsoft Managed Desktop 한 번만 변경을 적용합니다.<br>- 인증서 프로필, VPN 프로필 및 인증서 프로필을 구성하는 데 필요한 모든 Wi-Fi 업데이트합니다.

## <a name="device-wipe-with-factory-reset"></a>초기화 시 장치 지우기

이 Microsoft Managed Desktop 작업 팀은 필요한 경우 서비스에 등록된 장치의 공장 초기화 작업을 수행할 수 있습니다. 초기화는 다른 직원에게 장치를 제공해야 하는 경우나 직원이 퇴사하는 경우 유용합니다.

몇 가지 요구 사항이 있습니다.

- 전역 관리자는 서비스 요청을 제출해야 합니다.
- 요청에 디바이스의 컴퓨터 이름을 포함합니다.
- 디바이스를 초기화하기 전에 사용자 계정이 Azure AD에 있어야 합니다.

관리되는 데스크톱 작업 팀은 다음을 수행하게 됩니다.

- Intune에서 장치 이름 찾아 보기
- 장치에 공장 초기화 명령 보내기

> [!NOTE]
> 장치를 초기화하기 전에 Azure AD에서 사용자 계정을 제거하지 않습니다. 사용자가 Azure AD에 없는 경우 Intune에서 초기화 명령을 장치에 보낼 수 없습니다.

장치가 "첫 실행 경험"으로 부팅되고 사전 설치한 모든 응용 프로그램 및 설정이 다시 적용됩니다. 디바이스 사용자는 초기 설정 정보를 다시 제공해야 합니다. 

장치가 초기화되면 조직의 다른 사용자에 게 제공 할 수 있습니다. 이전 사용자의 데이터 또는 엔터프라이즈 데이터는 장치에 없습니다. 다음 사용자는 이전 사용자가 새 장치와 동일한 프로세스를 Microsoft Managed Desktop 합니다.

BitLocker는 이 프로세스에서 데이터 보안의 핵심 구성 요소입니다. 여러 장치에서 BitLocker Microsoft Managed Desktop 장치를 초기화한 후에도 드라이브의 데이터가 안전하게 유지됩니다. 드라이브에 있는 데이터는 장치의 다음 사용자가 사용할 수 없습니다. 자세한 내용은 [BitLocker 개요를 참조하세요.](/windows/security/information-protection/bitlocker/bitlocker-overview)

자세한 내용은 장치 [초기화 를 참조하세요.](/intune/remote-actions/devices-wipe#factory-reset-a-device)
