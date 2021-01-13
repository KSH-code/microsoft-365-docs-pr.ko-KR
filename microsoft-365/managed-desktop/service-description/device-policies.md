---
title: 장치 구성
description: Microsoft Managed Desktop 장치에 적용되는 기본 정책에 대해 자세히 알아보습니다.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 7086774c046ac28ffa467168e3b5b1affb508ec8
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840335"
---
# <a name="device-configuration"></a>장치 구성


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

새 Microsoft Managed Desktop 디바이스를 설정하는 경우 Microsoft Managed Desktop에 최적화된 적절한 구성이 적용되어 있습니다. 이 구성에는 온보더링 프로세스의 일부로 설정된 기본 정책 집합이 포함됩니다. 이러한 정책은 가능하면 MDM(모바일 장치 관리)을 사용하여 전달됩니다. 자세한 내용은 모바일 장치 [관리를 참조하세요.](https://docs.microsoft.com/windows/client-management/mdm/) 

>[!NOTE]
>충돌을 방지하기 위해 이러한 정책을 변경하지 않도록 합니다.

디바이스는 서명 이미지와 함께 도착한 다음 첫 번째 사용자가 로그인할 때 Azure Active Directory 도메인에 가입합니다. 장치는 IT 담당자의 개입 없이 필요한 정책 및 응용 프로그램을 자동으로 설치합니다.

## <a name="default-policies"></a>기본 정책

이 표에서는 장치 프로비전 중에 모든 Microsoft Managed Desktop 장치에 적용되는 기본 정책을 강조합니다. Microsoft Managed Desktop Operations Team에서 승인하지 않은 검색된 모든 변경 내용이 Microsoft Managed Desktop에서 관리되는 개체로 되버됩니다.

정책 | 설명
--- | ---
보안 기준 | [MDM에 대한 Microsoft](https://docs.microsoft.com/windows/device-security/windows-security-baselines) 보안 기준은 모든 Microsoft Managed Desktop 장치에 대해 구성됩니다. 이 기준은 업계 표준 구성입니다. Microsoft 보안 전문가가 최신 작업 공간에서 Microsoft Managed Desktop 장치 및 앱을 안전하게 유지하기 위해 공개적으로 릴리스되고, 잘 테스트되고, 검토되고 있습니다. <br><br>지속적으로 진화하는 보안 위협 환경의 위협을 완화하기 위해 Microsoft 보안 기준이 업데이트되고 각 Windows 10 기능 업데이트가 있는 Microsoft Managed Desktop 장치에 배포됩니다.<br><br>자세한 내용은 [Windows 보안 기준을 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)
Microsoft Managed Desktop 권장 보안 서식 파일 | 사용자 환경을 최적화하는 보안 기준에 대한 권장 변경 사항 집합입니다.  이러한 변경 내용은 보안 부록에 [설명되어 있습니다.](#security-addendum) 정책 부록에 대한 업데이트는 필요한 경우 발생합니다.  
업데이트 배포 | 비즈니스용 Windows 업데이트를 사용하여 소프트웨어 업데이트의 단계적 배포를 수행할 수 있습니다. IT 관리자는 배포 그룹 정책에 대한 설정을 수정할 수 없습니다. 그룹 기반 배포에 대한 자세한 내용은 [Microsoft Managed Desktop에서](updates.md)업데이트 처리 방법을 참조하세요.
데이터 연결 | 기본적으로 데이터 데이터 연결(예: LTE 네트워크)을 통해 업데이트는 꺼져 있습니다. 그러나 각 사용자는 설정 > 업데이트 및 고급 옵션에서 > **있습니다.** 데이터 연결에서 업데이트를 사용하도록 모든 사용자가 허용하려면 변경 [](../working-with-managed-desktop/admin-support.md)요청을 제출하면 모든 장치에 대해 이 설정이 켜지게 됩니다.
| 장치 준수 | 이러한 정책은 모든 Microsoft Managed Desktop 장치에 대해 구성됩니다. 디바이스가 필수 보안 구성에서 밝아진 경우 장치가 규격이 아닌 것으로 보고됩니다.

## <a name="windows-diagnostic-data"></a>Windows 진단 데이터

 장치는 알려진 상업용 식별자에 따라 Microsoft에 향상된 진단 데이터를 제공하게 설정됩니다. Microsoft Managed Desktop의 일부로 IT 관리자는 이러한 설정을 변경할 수 없습니다. GDPR(일반 데이터 보호 규정) 지역의 고객의 경우 사용자는 제공되는 진단 데이터의 수준을 줄일 수 있지만 서비스가 감소합니다. 예를 들어 Microsoft Managed Desktop은 성능 및 보안 요구 사항을 가장 잘 처리하기 위해 설정 및 정책을 이행하는 데 필요한 데이터를 수집할 수 없습니다. 자세한 내용은 [조직에서 Windows 진단 데이터 구성을 참조하세요.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>보안 부록

 이 섹션에서는 기본 정책에 나열된 표준 Microsoft Managed Desktop 정책 외에 배포될 정책에 [대해 간략하게 설명합니다.](#default-policies) 이 구성은 사용자 생산성을 유지하면서 최고 보안에 최적화된 금융 서비스 및 높은 규제 대상 산업을 염두에 두어 설계되었습니다.

 ### <a name="additional-security-policies"></a>추가 보안 정책

 이러한 정책은 높은 규제 대상 산업의 보안을 강화하기 위해 추가되었습니다. 
 - **보안 모니터링:** Microsoft는 [끝점용 Microsoft Defender를 사용하여 장치를 모니터링합니다.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 위협이 감지되면 Microsoft는 고객에게 알리고 장치를 격리하고 문제를 원격으로 해결합니다. 
 - **PowerShell V2를** 사용하지 않도록 설정: Microsoft는 2017년 8월 PowerShell V2를 제거했습니다. 이 기능은 모든 Microsoft Managed Desktop 장치에서 사용하지 않도록 설정되었습니다. 이 변경에 대한 자세한 내용은 [Windows PowerShell 2.0 사용되지 않습니다.](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/)
