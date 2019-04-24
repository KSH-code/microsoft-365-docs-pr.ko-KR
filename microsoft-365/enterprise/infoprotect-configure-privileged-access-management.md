---
title: '4단계: Office 365에 대한 권한이 부여된 액세스 관리 구성'
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Office 365에 대한 권한이 부여된 액세스 관리를 이해하고 구성합니다.
ms.openlocfilehash: 297d8e042c2a22c93b4ea566081d258e7ca0a5ab
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286951"
---
# <a name="step-4-configure-privileged-access-management-for-office-365"></a>4단계: Office 365에 대한 권한이 부여된 액세스 관리 구성

*이 단계는 선택 사항이며 Microsoft 365 Enterprise E5 및 Advanced Compliance 버전에만 적용됩니다.*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

권한이 부여된 액세스 관리는 Office 365 테넌트의 태스크 기반 활동에 대해 JIT(Just-In-Time) 액세스를 지정하는 정책을 구성하여 적용됩니다. 이 기능은 중요한 데이터에 대한 대기 없는 액세스 권한 또는 중요한 구성 설정에 대한 액세스 권한이 부여된 기존 관리자 계정을 사용할 수 있는 보안 위반으로부터 조직을 보호하는 데 도움이 될 수 있습니다. 예를 들어, Office 365 테넌트의 조직 사서함 설정을 액세스 및 변경하기 위해 명시적 승인을 요구하는 권한이 부여된 액세스 관리 정책을 구성할 수 있습니다.

이 단계에서는 Office 365 테넌트에서 액세스 권한이 부여된 액세스 관리를 사용하도록 설정하고, 조직의 Office 365 데이터 및 구성 설정에 대한 태스크 기반 액세스에 대해 추가 보안을 제공하는 권한이 부여된 액세스 정책을 구성합니다. Office 365 조직에서 권한이 부여된 액세스로 시작하려면 다음과 같은 3가지 기본 단계를 수행합니다.
- 승인자 그룹 만들기
- 권한 있는 액세스 사용
- 승인 정책 만들기

일단 구성되고 나면, 권한이 부여된 액세스 관리는 대기 없는 관리 액세스 권한 때문에 조직이 대기 없는 권한으로 작업하고, 발생하는 취약성에 대한 보안 계층을 제공할 수 있도록 합니다. 권한이 부여된 액세스의 경우 연결된 승인 정책이 정의된 작업을 실행하려면 승인이 필요합니다. 승인 정책에 포함된 작업을 실행해야 하는 사용자는 정책에 정의된 작업을 실행하는 데 필요한 권한을 얻기 위해 액세스 승인을 요청하고 받아야 합니다.

Office 365 권한이 부여된 액세스 관리를 사용하도록 설정하려면 [Office 365의 권한이 부여된 액세스 관리](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) 항목을 참조하세요.

자세한 내용은 [Office 365의 권한이 부여된 액세스 관리](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) 항목을 참조하세요.

## <a name="results"></a>결과

이 단계에서는 조직의 핵심 데이터 및 구성 설정에 대해 JIT(Just-In-Time) 액세스 제어를 사용하도록 설정하여 Office 365의 보안이 개선되었습니다.

중간 검사점으로 이 단계에 해당하는 [종료 조건](infoprotect-exit-criteria.md#crit-infoprotect-step5)을 확인하세요.

## <a name="next-step"></a>다음 단계

[정보 보호 인프라 종료 조건](infoprotect-exit-criteria.md)