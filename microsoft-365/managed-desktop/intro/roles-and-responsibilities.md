---
title: Microsoft Managed Desktop 역할 및 책임
description: 이 문서에서는 Microsoft Managed Desktop에 대해 Microsoft에서 제공하는 역할 및 책임에 대해 설명합니다.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 94389fbb9a13b9a880b0c4dcaf67d8adcaff0f98
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841318"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Microsoft Managed Desktop 역할 및 책임


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

조직이 Microsoft Managed Desktop에 등록된 경우 Microsoft는 어떤 작업을 하나요? 조직의 책임은 무엇입니까?

## <a name="microsofts-roles-and-responsibilities"></a>Microsoft의 역할 및 책임

Microsoft는 다음 주요 역할 및 책임을 제공합니다.

역할 또는 책임 | 설명
--- | ---
MDM 정책 관리 | Microsoft는 모범 사례에 따라 MDM 정책을 적용하고 정책 변경 요청을 고려합니다. 또한 장치 정책에 설명된 따라 테넌트도 [변경합니다.](../service-description/device-policies.md)
사용자 지원 | 모든 Microsoft Managed Desktop 디바이스에 미리 설치되는 도움말 보기 앱을 통해 등록된 모든 사용자에 대해 장치, Windows 및 엔터프라이즈용 Microsoft 365 앱 제품 제품군에 대한 사용자 지원을 제공합니다. 
Microsoft Managed Desktop 서비스 지원 | Microsoft는 Microsoft Managed Desktop Operations Team을 통해 IT 부서에 지원을 제공합니다. 이 팀은 고객의 Microsoft Managed Desktop 환경에 대한 기술 문제 해결, 변경 요청 및 인시던트 관리를 지원할 것입니다. 자세한 내용은 [Microsoft Managed Desktop에 대한 관리자 지원을 참조하세요.](../working-with-managed-desktop/admin-support.md)
보안 모니터링 | Microsoft는 끝점용 Microsoft Defender를 사용하여 Microsoft Managed Desktop 장치를 모니터링합니다. Microsoft SOC(Managed Desktop Security Operations Center)가 위협을 감지하는 경우 Microsoft는 사용자에게 알리고 장치를 격리하고 문제를 원격으로 해결합니다. 자세한 내용은 Security 를 [참조하십시오.](../service-description/security.md)
모니터링 및 관리 업데이트 | Microsoft Windows 및 Windows용 최신 품질 및 기능 업데이트가 설치되도록 Microsoft Managed Desktop 장치를 적극적으로 Microsoft Office. 자세한 내용은 업데이트 처리 [방법을 참조하세요.](../service-description/updates.md)
사용자 및 장치 그룹화 | Microsoft Managed Desktop 운영 팀은 IT 작업의 일부로 필요한 장치 및 사용자 그룹을 만들고 관리합니다. 이러한 그룹에는 구성원 자격 또는 구성 변경이 허용되지 않습니다. 이러한 그룹을 변경하면 디바이스가 예기치 않게 구성되어 기능이 손실될 수 있습니다. 일단 설정되면 이러한 그룹에 대한 문제나 질문이 있으면 IT 관리자가 Microsoft Managed Desktop 작업에 문의할 수 있습니다. 자세한 내용은 [Microsoft Managed Desktop에 대한 관리자 지원을 참조하세요.](../working-with-managed-desktop/admin-support.md)

## <a name="your-roles-and-responsibilities"></a>사용자 역할 및 책임

이 일반적인 역할 및 책임 집합은 배포에 필요하지만 Microsoft에서 제공하지는 않습니다. 이 모든 것은 아니며 대부분의 조직에 적용할 수 있습니다. 사용자와 Microsoft가 모두 책임을 공유하는 몇 가지 항목이 있습니다. 

역할 또는 책임 | 설명
--- | ---
변경 관리 | Microsoft는 Microsoft Managed Desktop 환경을 변경해야 하는 경우 사전에 고객에게 알립니다. 자세한 내용은 서비스 변경 [및 통신을 참조하세요.](../service-description/servicechanges.md)<br><br>직접 변경 관리 프로세스를 수행하고 Microsoft Managed Desktop Operations 팀과 함께 연락처를 설정해야 합니다. 또한 이러한 변경 내용을 검토하고 승인하기 위한 리소스도 있어야 합니다. 자세한 내용은 작업 및 [모니터링을 참조하십시오.](../service-description/operations-and-monitoring.md)  
ID 관리 | 사용자 계정을 만들고, 사용자를 그룹에 할당하고, 메타데이터를 최신으로 유지할 책임이 있습니다. 
엔터프라이즈용 Microsoft 365 앱 구성 및 관리 | Microsoft는 사용자에게 Office 응용 프로그램을 배포하고 해당 응용 프로그램을 최신으로 유지하도록 할 책임이 있습니다. <br><br> Exchange Online 관리 책임을 포함하여 Microsoft 365 서비스 및 정책을 관리할 책임은 다음을 담당합니다.<br>- 전자 메일 관리<br>- 사서함 및 규칙 구성<br>- Exchange-프레미스 관리<br><br>또한 Microsoft 365 관리 센터에 설정된 공동 작업 도구, SharePoint 서버 관리, 도메인 관리 및 보안 및 정보 정책을 담당합니다. 
사용자 지원 | 다음에 대한 사용자 지원을 제공해야 합니다. <br>- 사이트 인프라: 모든 네트워크 및 인터넷 연결, VPN 인프라 및 클라이언트 구성, 로컬 회의실 장비, 프린터, 프록시 서버 및 구성 및 방화벽<br><br>- 회사 전체의 클라우드 리소스: 전자 메일, SharePoint, 공동 작업 서비스 및 회사 전사적 기술 공간과 관련된 기타 클라우드 인프라<br><br>- 업무(LINE) 및 기타 회사별 응용 프로그램
앱 | 역할 및 책임은 Microsoft Managed Desktop의 일부로 제공되는 앱과 사용자가 제공하는 앱에 대해 다소 다릅니다. <br><br>Microsoft에서 제공하는 앱(Word, Excel, PowerPoint, Outlook, Publisher, Access, 비즈니스용 Skype, Teams 및 OneNote를 구성하는 엔터프라이즈용 Microsoft 365 앱)의 경우 **Microsoft는** 배포, 업데이트 및 지원을 위한 전체 서비스를 제공합니다. **이러한** 앱에 대한 라이선스를 획득하여 할당하고, 보안 그룹에 사용자를 추가하고, 수명 종료를 관리하고 필요한 추가 기능을 배포해야 합니다.<br><br>사용자가 제공하는 앱(예: 업무용 앱)의 경우 패키지를 직접 패키지로 되거나 Microsoft가 아닌 다른 공급업체에 문의하는 경우 다음 작업을 담당합니다.  <br><br>- 대상 사용자 그룹에 필요한 응용 프로그램 식별<br>- 앱 배포를 위한 Azure AD 그룹 만들기 및 관리<br>- Microsoft Intune 배포 표준을 충족하는 앱 패키징<br>- Microsoft Intune에 앱 업로드<br>- Microsoft Managed Desktop 환경에서 앱 테스트<br>- 사용자와 앱 테스트<br>- 응용 프로그램 관리 및 사용자 할당<br>- Microsoft Intune을 통해 응용 프로그램 업데이트 식별 및 배포<br>- 응용 프로그램이 사용 중지된 경우 응용 프로그램 제거 및 제거<br>- 라이선스 조달 및 할당<br>- 업무 앱에 대한 사용자 지원 제공<br>- 원격으로 앱 설정 관리<br><br>**Microsoft는** 원격 클라이언트에 응용 프로그램을 전달하는 Microsoft Intune 배포 도구를 제공합니다.<br><br>자세한 내용은 앱을 [참조하세요.](../get-ready/apps.md)
보안 모니터링 및 대응 | Microsoft Managed Desktop 장치가 아닌 장치에 대한 인시던트 조사 및 해결과 Microsoft Managed Desktop Operations Team이 서비스에 영향을 줄 수 있는 문제를 알릴 책임이 있습니다.
작업 지원 | 조직의 기본 연락처 및 주제 전문가 목록을 제공해야 합니다. Microsoft Managed Desktop과 관련 없는 운영 인시던트가 있는 경우 이러한 연락처가 필요합니다. <br><br>또한 Microsoft Managed Desktop에 없는 장치 및 서비스에 대한 인시던트 조사 및 문제를 조사하고 문제의 원인을 밝히고 Microsoft Managed Desktop Operations Team에 항상 정보를 제공해야 합니다.
VPN을 포함한 네트워크 인프라 | 인터넷 연결, 네트워크 제어, 프록시 구성 및 원격 연결 인프라를 비롯한 모든 네트워킹 관련 인프라 및 서비스의 설정, 구성 및 관리(문제 해결 및 디버깅 포함)를 담당합니다.<br><br>프록시가 구성된 경우(하드웨어 또는 소프트웨어에서) 프록시에서 허용해야 하는 URL 컬렉션이 있습니다. 여러 개의 proxies로 인한 충돌 또는 비호호성 문제를 해결할 책임이 있습니다. 구성 가능한 설정을 사용하여 조직에 특정한 네트워크 Proxies를 추가할 수 있습니다. 자세한 내용은 구성 가능한 설정을 [참조하십시오.](../working-with-managed-desktop/config-setting-ref.md#proxy)<br><br>자세한 내용은 [프록시 구성을 참조하세요.](../get-ready/network.md)
인쇄 | 프린터 및 인쇄 큐를 설치, 유지 관리 및 관리할 책임이 있습니다. 클라우드 인쇄는 권장되는 솔루션이지만 필수는 아닙니다. 




