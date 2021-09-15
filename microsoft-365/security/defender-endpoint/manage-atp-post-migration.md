---
title: 마이그레이션 후 끝점에 대한 Microsoft Defender 관리
description: 끝점용 Microsoft Defender로 전환한 후 다음 단계는 위협 방지 기능을 관리하는 것입니다.
keywords: 마이그레이션 후, 관리, 운영, 유지 관리, 사용률, 끝점용 Microsoft Defender, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: conceptual
ms.date: 01/26/2021
ms.reviewer: chventou
ms.openlocfilehash: 77777de720d369c09f62d4a7e17e8b4cf5a3519b
ms.sourcegitcommit: f88a0ec621e7d9bc5f376eeaf70c8a9800711f88
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2021
ms.locfileid: "59356828"
---
# <a name="manage-microsoft-defender-for-endpoint-post-migration"></a>끝점용 Microsoft Defender 관리, 마이그레이션 후

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

이전 끝점 보호 및 바이러스 백신 솔루션에서 끝점용 Microsoft Defender로 이동한 후 다음 단계는 기능과 기능을 관리하는 것입니다. 조직의 장치 [Microsoft Endpoint Manager](/mem/endpoint-manager-overview)보안 설정을 [](/mem/intune/fundamentals/what-is-intune) 관리하려면 Microsoft Intune [](/mem/configmgr/core/understand/introduction)및 Microsoft Endpoint Configuration Manager 를 사용하는 것이 좋습니다. 그러나 도메인 서비스 에서 그룹 정책 개체와 같은 다른 [도구/메서드를 Azure Active Directory 있습니다.](/azure/active-directory-domain-services/manage-group-policy)

다음 표에는 사용할 수 있는 다양한 도구/방법과 자세한 내용을 볼 수 있는 링크가 나열됩니다.

<br/><br/>

|도구/메서드|설명|
|---|---|
|**[취약성 관리 포털의](/windows/security/threat-protection/microsoft-defender-atp/tvm-dashboard-insights)** 위협 및 Microsoft 365 Defender [정보](https://security.microsoft.com/)|위협 & 취약성 관리 대시보드는 보안 운영 팀이 노출을 줄이고 조직의 보안 자세를 개선하는 데 사용할 수 있는 실행 가능한 정보를 제공합니다. <p> 위협 [& 취약성 관리](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) 및 의 [개요를 Microsoft 365 Defender.](/microsoft-365/security/defender-endpoint/use)|
|**[Microsoft Intune(권장)](/mem/intune/fundamentals/what-is-intune)**|Microsoft Intune 구성 요소인 Intune(Microsoft Endpoint Manager)은 MDM(모바일 장치 관리) 및 MAM(모바일 응용 프로그램 [관리)에](/mem/endpoint-manager-overview)중점을 니다. Intune을 사용하면 휴대폰, 태블릿 및 노트북을 포함하여 조직의 장치가 사용되는 방법을 제어할 수 있습니다. 응용 프로그램을 제어하도록 특정 정책을 구성할 수도 있습니다. <p> [Intune을 사용하여 끝점용 Microsoft Defender 관리를 참조합니다.](manage-atp-post-migration-intune.md)|
|**[Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction)**|Microsoft Endpoint Manager(Configuration Manager)는 System Center Configuration Manager 의 구성 [Microsoft Endpoint Manager.](/mem/endpoint-manager-overview) Configuration Manager는 사용자, 장치 및 소프트웨어를 관리하는 강력한 도구입니다. <p> Configuration Manager를 사용하여 [끝점용 Microsoft Defender 관리를 참조합니다.](manage-atp-post-migration-configuration-manager.md)|
|**[Azure Active Directory 도메인 서비스의 그룹 정책 개체](/azure/active-directory-domain-services/manage-group-policy)**|[Azure Active Directory 도메인 서비스에는](/azure/active-directory-domain-services/overview) 사용자 및 장치에 대한 기본 제공 그룹 정책 개체가 포함되어 있습니다. 환경에 필요한 경우 기본 제공 그룹 정책 개체를 사용자 지정할 수 있으며 사용자 지정 그룹 정책 개체 및 US(조직 구성 단위)를 만들 수 있습니다. <p> 그룹 정책 개체를 사용하여 [끝점용 Microsoft Defender 관리를 참조합니다.](manage-atp-post-migration-group-policy-objects.md)|
|**[PowerShell, WMI 및 MPCmdRun.exe](manage-atp-post-migration-other-tools.md)**|*조직의 Microsoft Endpoint Manager 위협 방지 기능을 관리하기 위해 Intune 및 Configuration Manager를 포함하는 보안 설정을 사용하는 것이 좋습니다. 그러나 PowerShell, WMI 또는 MPCmdRun.exe 사용하여 개별 디바이스(끝점)의 Microsoft Defender 바이러스 백신 설정과 같은 일부 설정을 구성할 MPCmdRun.exe 있습니다.* <p> PowerShell을 사용하여 공격 Microsoft Defender 바이러스 백신 보호 및 공격 표면 감소 규칙을 관리할 수 있습니다. [PowerShell을 통해 끝점에 대한 Microsoft Defender 구성을 참조합니다.](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-powershell) <p> WMI(Windows Management Instrumentation)를 사용하여 제외를 Microsoft Defender 바이러스 백신 수 있습니다. [WMI를 통해 끝점에 대한 Microsoft Defender 구성을 참조합니다.](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi) <p> Microsoft 맬웨어 보호 Command-Line 유틸리티(MPCmdRun.exe)를 사용하여 Microsoft Defender 바이러스 백신 및 제외를 관리하고 네트워크와 클라우드 간의 연결 유효성을 검사할 수 있습니다. 자세한 [내용은 Configure Microsoft Defender for Endpoint with MPCmdRun.exe. ](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe)|

## <a name="see-also"></a>참고 항목

- [Endpoint용 Microsoft Defender에서 가양성/가음성 처리](defender-endpoint-false-positives-negatives.md)
