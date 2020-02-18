---
title: '4단계: WIP(Windows Information Protection) 구성'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365에서 WIP(Windows Information Protection) 이해 및 배포
ms.openlocfilehash: 655ff33c3fd1bba822937618d801db76b7881977
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067165"
---
# <a name="step-4-configure-windows-information-protection"></a>4단계: WIP(Windows Information Protection) 구성

*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

![6단계: 정보 보호](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

더 많은 개인 장치를 작업에 사용할 수 있으므로, 개인 조직 데이터를 누출할 수 있는 앱 및 장치의 위험이 높아졌습니다. 예를 들어, 직원이 실수로 미래 제품에 대한 마케팅 계획의 사진을 소셜 미디어에 전송하거나 매우 중요한 정보를 공개 클라우드 스토리지에 저장합니다. 

WIP(Windows Information Protection)를 사용하여 Windows 10 장치에서 이러한 유형의 데이터 누출을 방지할 수 있습니다. 자세한 내용은 [WIP를 사용한 엔터프라이즈 데이터 보호](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)를 참조하세요.

Microsoft 365 Enterprise에서, WIP는 구독에 포함된 Windows 10 Enterprise 및 Microsoft Intune의 조합입니다. 

Microsoft 365 Enterprise와 함께 조직에 WIP를 배포하려면 다음을 수행합니다.

1. Intune에 Windows 장치를 등록합니다. [5단계: 모바일 장치 관리](mobility-infrastructure.md)에서 이 작업을 했어야 합니다.
2. [WIP용 Intune 정책](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure)을 만듭니다.
  - 제한된 앱 목록을 작성했는지 확인합니다.
  - WIP 보호 수준을 선택합니다.

[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm)에서 WIP를 사용할 수도 있습니다. 

자세한 내용은 [WIP 모범 사례]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip)를 참조하세요.

중간 검사점으로 이 단계에 해당하는 [종료 조건](infoprotect-exit-criteria.md#crit-infoprotect-step4)을 확인하세요.

## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![5단계](../media/stepnumbers/Step5.png)|[Office 365 데이터 손실 방지 구성](infoprotect-data-loss-prevention.md)|


