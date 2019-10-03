---
title: Windows 10 Enterprise 보안 기능 배포
description: Microsoft 365 Enterprise의 일부로 Pc에 Windows 10 Enterprise 보안 기능을 배포 하는 데 필요한 단계에 대 한 간략 한 지침을 제공 합니다.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 설명서, Windows 10 Enterprise, security
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: greglin
ms.openlocfilehash: 0f7b4ddec9c52861b4ecf4a7e86831efcce402d6
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370265"
---
# <a name="step-5-deploy-windows-10-enterprise-security-features"></a>5 단계: Windows 10 Enterprise 보안 기능 배포

![3단계: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Windows 10에서는 보안 기능을 통해 엔터프라이즈 사용자를 보호 하 고, cyberthreats을 중지 하 고, 데이터 손실을 방지할 수 있습니다. 

이러한 기술에 대 한 자세한 내용은 다음 항목을 참조 하십시오.

* [Id 보호](https://docs.microsoft.com/windows/security/identity-protection/) -비즈니스용 Windows Hello, Credential Guard 및 액세스 제어에 대해 알아봅니다.
* [위협 방지](https://docs.microsoft.com/windows/threat-protection/) -Microsoft Defender Advanced Threat protection, 예방적 보호를 위한 통합 플랫폼, 위반 감지, 자동화 된 조사 및 응답에 대해 알아봅니다.
* [정보 보호](https://docs.microsoft.com/windows/security/information-protection/) -windows 10에서 엔터프라이즈 데이터를 보호 하는 데 도움이 되는 BitLocker, Windows Information protection 및 기타 방법에 대해 알아봅니다. 

이 단계에서는 다음 보안 기능을 사용 하 여 배포, 관리, 구성 및 문제 해결을 수행 하는 방법을 설명 합니다.

* [Windows Defender Antivirus](#windows-defender-antivirus)
* [Windows Defender Exploit Guard](#windows-defender-exploit-guard)
* [Microsoft Defender Advanced Threat Protection](#windows10-sec-atp)

<a name="windows10-sec-av"></a>
## <a name="windows-defender-antivirus"></a>Windows Defender Antivirus
Windows Defender 바이러스 백신 (AV)은 Windows 10에 기본적으로 제공 되는 맬웨어 방지 솔루션입니다. 데스크톱, 휴대용 컴퓨터 및 서버에 대 한 보안 및 맬웨어 방지 관리를 제공 합니다. Windows Defender AV에 대 한 자세한 내용과 최소 요구 사항과이 기능을 관리 하는 방법에 대 한 자세한 내용은 windows [10의 Windows Defender 바이러스 백신 및 Windows Server 2016](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)를 참조 하세요.

기본 바이러스 백신 클라이언트로 Windows Defender AV를 사용 하지 않거나 Microsoft Defender ATP도 사용 하는 경우 고려해 야 할 몇 가지 사항이 있습니다. 자세한 내용은 [Windows DEFENDER AV 호환성](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility)을 참조 하십시오.

### <a name="deployment-and-management"></a>배포 및 관리
Windows Defender AV를 배포 하 고 관리 하려면 다음 지침을 따르세요.

* [Windows Defender AV에 대 한 배포, 관리 및 보고](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [관리 및 구성 도구에 대 한 참조 항목](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

### <a name="configuration"></a>구성
사용자는 여러 기능을 구성할 수 있습니다. 자세한 내용은 다음 리소스를 참조 하세요.

* [Windows Defender AV 기능 구성](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)
* [관리 및 구성 도구에 대 한 참조 항목](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

구성 옵션을 이해 하려면 그룹 정책 구성에 정의 된 대로 모든 설정 목록을 참조 하세요. [그룹 정책 설정을 사용 하 여 Windows DEFENDER AV 구성 및 관리](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)

[Windows DEFENDER av 보호 평가 가이드](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus) 를 사용 하 여 네트워크에서 WINDOWS defender av의 보호 수준 및 영향을 평가할 수 있습니다. 이는 초기 구성 또는 ' 빠른 시작 가이드 '를 만드는 데도 유용 하며, 최대 보호를 위해 기능을 구성 및 사용 하도록 설정 하는 데 가장 적합 한 권장 사항을 제공 하기 위해 정기적으로 업데이트 됩니다.

### <a name="reporting"></a>보고
System Center Configuration Manager 또는 Microsoft Intune과 같은 구성 도구를 사용 하 여 보고를 가져올 수 있습니다. 또한 OMS (업데이트 준수)를 사용 하거나, SIEM에서 Windows 이벤트 로그를 사용 하 여 보고를 받을 수도 있습니다. Microsoft Defender ATP에 대 한 라이선스가 있는 경우 Windows Defender AV 검색에 보고 하 고 기본 수정을 수행할 수도 있습니다. 자세한 내용은 다음 리소스를 참조 하세요.
* [Windows Defender AV에 대 한 배포, 관리 및 보고](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Windows Defender AV 보호에 대 한 보고서](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/report-monitor-windows-defender-antivirus)
* [Microsoft Defender ATP 포털 개요](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>문제 해결
오류 및 이벤트 코드의 기본적인 문제 해결에 대 한 자세한 내용은 preview [이벤트 로그 및 오류 코드를 검토 하 여 Windows DEFENDER AV 관련 문제를 해결](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus)합니다.

Windows Defender 보안 인텔리전스 전송 시스템을 사용 하 여 가양성 등의 문제를 제출할 수도 있습니다. 자세한 내용은 [Microsoft로 문제 제출](https://www.microsoft.com/wdsi/filesubmission)를 참조 하십시오.

<a name="windows10-sec-eg"></a>
## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard
Windows Defender Exploit Guard는 Windows 10의 새로운 호스트 침입 방지 기능 집합입니다. Windows Defender Exploit Guard, 최소 요구 사항 및이 기능을 관리 하는 방법에 대 한 자세한 내용은 [Windows Defender Exploit guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard)를 참조 하십시오.

### <a name="deployment-management-and-configuration"></a>배포, 관리 및 구성
Windows Defender Exploit Guard를 배포, 관리 및 구성 하려면 다음 지침을 따르세요.
* [악용 방지](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/exploit-protection-exploit-guard)
* [공격 노출 영역 보호](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard?ocid=cx-docs-msa4053440)
* [네트워크 보호](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
* [제어 되는 폴더 액세스](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)

여러 평가 항목을 사용 하 여 네트워크에서 Windows Defender Exploit Guard의 보호 수준 및 영향을 평가 하는 데 도움이 되는 정보를 확인할 수 있습니다. 이는 초기 구성 또는 ' 빠른 시작 가이드 '를 만들 때 유용 하며, 최대 보호를 위해 기능을 구성 및 사용 하도록 설정 하는 데 가장 유용한 권장 사항을 제공 하기 위해 정기적으로 업데이트 됩니다. 자세한 정보는 [Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard)를 확인 하세요.

### <a name="reporting"></a>보고
System Center Configuration Manager 또는 Intune과 같은 구성 도구를 사용 하 여 보고를 받을 수 있습니다. 또한 SIEM에서 Windows 이벤트 로그를 사용 하 여 보고를 받을 수 있습니다. Microsoft Defender ATP에 대 한 라이선스가 있는 경우 Windows Defender AV 검색에 보고 하 고 기본 수정을 수행할 수도 있습니다. 자세한 내용은 다음 리소스를 참조 하세요.
* [Windows Defender Exploit Guard 이벤트 보기](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/event-views-exploit-guard)
* [Microsoft Defender ATP 포털 개요](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>문제 해결
Windows Defender 보안 인텔리전스 전송 시스템을 사용 하 여 기본 문제 해결을 수행 하거나 필요에 따라 Microsoft에 .cab 파일을 제공 하 고 문제를 전송 (예: 가양성) 할 수 있습니다. 자세한 내용은 [Microsoft로 문제 제출](https://www.microsoft.com/wdsi/filesubmission)를 참조 하십시오.


<a name="windows10-sec-atp"></a>
## <a name="microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection
Microsoft Defender ATP는 Microsoft 365 Enterprise E5 요금제 에서만 사용할 수 있으며, 엔터프라이즈 고객이 네트워크에서 advanced threat를 검색, 조사 및 응답할 수 있도록 하는 보안 서비스입니다. Microsoft Defender ATP에 대 한 자세한 내용과 최소 요구 사항 및이 기능을 관리 하는 방법에 대 한 자세한 내용은 다음 항목을 참조 하십시오.

* [Microsoft Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
* [최소 요구 사항](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/minimum-requirements-windows-defender-advanced-threat-protection)

### <a name="deployment-management-and-configuration"></a>배포, 관리 및 구성
Microsoft Defender ATP를 배포 하려면 올바른 Windows 라이선스가 있는지 확인 해야 합니다. 적절 한 라이선스가 있는지 확인 한 후에는 데이터를 저장할 위치를 결정 해야 합니다. 그런 후에는 온 보 딩 끝점을 서비스에 대해 시작할 수 있습니다.

이러한 단계에 대 한 자세한 내용은 다음 주요 항목을 참조 하십시오. 

* [라이선스 프로비저닝 확인 및 완료 설정](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/licensing-windows-defender-advanced-threat-protection)
* [데이터 저장 및 개인 정보](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/data-storage-privacy-windows-defender-advanced-threat-protection)
* [온보드 끝점 및 설치 액세스](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/onboard-configure-windows-defender-advanced-threat-protection)

### <a name="detect-investigate-respond"></a>검색, 조사, 응답
서비스에 대 한 끝점의 온 보 딩이 완료 되 면 다양 한 대시보드에서 알림 조사를 시작할 수 있습니다. 알림을 조사한 후에는 경고에 대해 응답 작업을 수행할 수 있습니다. 

이러한 작업을 수행 하는 방법에 대 한 자세한 내용은 다음을 참조 하십시오.
* [Microsoft Defender ATP 포털 개요](https://go.microsoft.com/fwlink/?linkid=861596)
* [Microsoft Defender ATP 포털 사용](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-windows-defender-advanced-threat-protection)
* [응답 작업 수행](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/response-actions-windows-defender-advanced-threat-protection)

### <a name="integrate-with-other-products-and-tools"></a>다른 제품 및 도구와 통합
Microsoft Defender ATP는 다양 한 제품 및 도구를 통합 하 고 해당 보안 기능을 확장 합니다. 

도구 및 기타 제품에 대 한 자세한 내용은 다음 항목을 참조 하십시오.
* [SIEM 도구](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection)
* [사용자 지정 알림 만들기](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-custom-ti-windows-defender-advanced-threat-protection)
* [Api 사용](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/exposed-apis-windows-defender-advanced-threat-protection)
* [Power BI 보고서 작성](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/powerbi-reports-windows-defender-advanced-threat-protection)

### <a name="troubleshooting"></a>문제 해결
온 보 딩 또는 제품을 사용 하는 동안 문제가 발생할 수 있습니다. 문제를 해결 하는 방법에 대 한 자세한 내용은 다음 항목을 참조 하십시오.
* [온 보 딩 문제 해결](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-onboarding-windows-defender-advanced-threat-protection)
* [Microsoft Defender ATP 문제 해결](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-windows-defender-advanced-threat-protection)

## <a name="next-step"></a>다음 단계

[Windows 10 Enterprise 인프라 종료 조건](windows10-exit-criteria.md)
