---
title: '7단계: Office 365에 대한 권한이 부여된 액세스 관리 구성'
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Office 365에 대한 권한이 부여된 액세스 관리를 이해하고 구성합니다.
ms.openlocfilehash: f29b1e0934a4b9a6d4e3347584f39423d446ed58
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067235"
---
# <a name="step-7-configure-privileged-access-management-for-office-365"></a>7단계: Office 365에 대한 권한이 부여된 액세스 관리 구성

*이 단계는 선택 사항이며 Microsoft 365 Enterprise E5 및 Advanced Compliance 버전에만 적용됩니다.*

![6단계: 정보 보호](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

권한이 부여된 액세스 관리는 Office 365 테넌트의 태스크 기반 활동에 대해 JIT(Just-In-Time) 액세스를 지정하는 정책을 구성하여 적용됩니다. 이 기능은 중요한 데이터에 대한 대기 없는 액세스 권한 또는 중요한 구성 설정에 대한 액세스 권한이 부여된 기존 관리자 계정을 사용할 수 있는 보안 위반으로부터 조직을 보호하는 데 도움이 될 수 있습니다. 예를 들어, Office 365 테넌트의 조직 사서함 설정을 액세스 및 변경하기 위해 명시적 승인을 요구하는 권한이 부여된 액세스 관리 정책을 구성할 수 있습니다.

이 단계에서는 Office 365 테넌트에서 액세스 권한이 부여된 액세스 관리를 사용하도록 설정하고, 조직의 Office 365 데이터 및 구성 설정에 대한 태스크 기반 액세스에 대해 추가 보안을 제공하는 권한이 부여된 액세스 정책을 구성합니다. Office 365 조직에서 권한이 부여된 액세스로 시작하려면 다음과 같은 3가지 기본 단계를 수행합니다.
- 승인자 그룹 만들기
- 권한 있는 액세스 사용
- 승인 정책 만들기

일단 구성되고 나면, 권한이 부여된 액세스 관리는 대기 없는 관리 액세스 권한 때문에 조직이 대기 없는 권한으로 작업하고, 발생하는 취약성에 대한 보안 계층을 제공할 수 있도록 합니다. 권한이 부여된 액세스의 경우 연결된 승인 정책이 정의된 작업을 실행하려면 승인이 필요합니다. 승인 정책에 포함된 작업을 실행해야 하는 사용자는 정책에 정의된 작업을 실행하는 데 필요한 권한을 얻기 위해 액세스 승인을 요청하고 받아야 합니다.

Office 365 권한이 부여된 액세스 관리를 사용하도록 설정하려면 [Office 365의 권한이 부여된 액세스 관리](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) 항목을 참조하세요.

자세한 내용은 [Office 365의 권한이 부여된 액세스 관리](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) 항목을 참조하세요.


|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  테스트 랩 환경에서 이 구성을 연습하려면 [권한이 부여된 액세스 관리 테스트 랩 가이드](privileged-access-microsoft-365-enterprise-dev-test-environment.md)를 참조하세요. |
|||

중간 검사점으로 이 단계에 해당하는 [종료 조건](infoprotect-exit-criteria.md#crit-infoprotect-step7)을 확인하세요.

## <a name="next-step"></a>다음 단계

[정보 보호 인프라 종료 조건](infoprotect-exit-criteria.md)
