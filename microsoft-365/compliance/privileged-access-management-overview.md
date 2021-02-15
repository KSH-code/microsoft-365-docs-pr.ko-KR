---
title: 권한이 부여된 액세스 관리에 대한 자세한 정보
description: 이 문서에서는 FAQ(질문과 대답)를 포함하여 Microsoft 365의 권한이 부여된 액세스 관리에 대한 개요를 제공합니다.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
f1.keywords:
- NOCSH
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.openlocfilehash: 059e1653d7db9140dbc80fd69fe36e95a744b079
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126607"
---
# <a name="learn-about-privileged-access-management"></a>권한이 부여된 액세스 관리에 대한 자세한 정보

권한이 부여된 액세스 관리를 사용하면 Office 365의 권한 있는 관리 작업에 대한 세부적인 액세스 제어가 허용됩니다. 중요한 데이터에 대한 액세스 또는 중요한 구성 설정에 대한 액세스 권한이 있는 기존 권한 있는 관리자 계정을 사용하는 위반으로부터 조직을 보호하는 데 도움이 될 수 있습니다. 권한이 부여된 액세스 관리를 사용하려면 사용자가 범위가 넓고 시간이 제한적인 승인 워크플로를 통해 권한 상승 및 권한 있는 작업을 완료하기 위해 적시 액세스를 요청해야 합니다. 이 구성을 사용하면 중요한 데이터나 중요한 구성 설정이 노출되지 않고도 작업을 수행할 수 있는 충분한 액세스 권한을 사용자에게 제공합니다. Microsoft 365에서 권한이 부여된 액세스 관리를 사용하도록 설정하면 조직이 제로 스위딩 권한으로 운영할 수 있으며, 관리 액세스 취약성에 대한 방어 계층을 제공할 수 있습니다.

통합된 고객 Lockbox 및 권한이 부여된 액세스 관리 워크플로에 대한 간략한 개요는 고객 Lockbox 및 권한이 부여된 액세스 관리 비디오를 [참조하세요.](https://go.microsoft.com/fwlink/?linkid=2066800)

## <a name="layers-of-protection"></a>보호 계층

권한 있는 액세스 관리는 Microsoft 365 보안 아키텍처 내의 다른 데이터 및 액세스 기능 보호를 보완합니다. 권한 있는 액세스 관리를 보안에 대한 통합 및 계층적 접근 방식의 일부로 포함하면 중요한 정보 및 Microsoft 365 구성 설정의 보호를 최대화하는 보안 모델이 있습니다. 다이어그램에 표시된 것 처럼 권한 있는 액세스 관리는 Microsoft 365 데이터의 기본 암호화와 Microsoft 365 서비스의 역할 기반 액세스 제어 보안 모델과 함께 제공되는 보호 기능을 기반으로 합니다. [Azure AD Privileged Identity Management와](/azure/active-directory/active-directory-privileged-identity-management-configure)함께 사용하는 경우 이러한 두 기능은 서로 다른 범위에서 Just-In-Time 액세스를 통해 액세스 제어를 제공합니다.

![Microsoft 365의 계층적 보호](../media/pam-layered-protection.png)

권한 있는 액세스 관리는 작업  수준에서 정의되고 범위가 지정되는 반면, Azure  AD Privileged Identity Management는 여러 작업을 실행하는 기능을 사용하여 역할 수준에서 보호를 적용합니다. Azure AD Privileged Identity Management는 주로 AD 역할 및 역할 그룹에 대한 액세스를 관리할 수 있도록 하지만 Microsoft 365의 권한 있는 액세스 관리는 작업 수준에서만 적용됩니다.

- **Azure AD Privileged Identity Management를** 이미 사용하는 동안 권한 있는 액세스 관리를 사용하도록 설정: 권한 있는 액세스 관리를 추가하면 Microsoft 365 데이터에 대한 권한 있는 액세스에 대한 또 다른 세부적인 보호 및 감사 기능을 제공합니다.

- **Office 365에서**  권한 있는 액세스 관리를 이미 사용하는 동안 Azure AD Privileged Identity Management를 사용하도록 설정:  Azure AD Privileged Identity Management를 권한 있는 액세스 관리에 추가하면 주로 사용자 역할 또는 ID에 의해 정의된 Microsoft 365 외부의 데이터에 대한 권한 있는 액세스를 확장할 수 있습니다.  

## <a name="privileged-access-management-architecture-and-process-flow"></a>권한이 부여된 액세스 관리 아키텍처 및 프로세스 흐름

다음의 각 프로세스 흐름에서는 권한이 부여된 액세스의 아키텍처와 Microsoft 365의 기하 도형, 감사 및 Exchange 관리 실행 영역과 상호 작용하는 방법을 간략하게 설명합니다.

### <a name="step-1-configure-a-privileged-access-policy"></a>1단계: 권한 있는 액세스 정책 구성

[Microsoft 365](https://admin.microsoft.com) 관리 센터 또는 Exchange 관리 PowerShell을 사용하여 권한 있는 액세스 정책을 구성할 때 Microsoft 365 기술에 권한 있는 액세스 기능 프로세스 및 정책 특성을 정의합니다. 활동은 보안 준수 센터에 &amp; 기록됩니다. 이제 정책이 사용하도록 설정되어 승인을 위해 들어오는 요청을 처리할 준비가 됩니다.

![1단계: 정책 만들기](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>2단계: 액세스 요청

Microsoft [365](https://admin.microsoft.com) 관리 센터 또는 Exchange 관리 PowerShell을 통해 사용자는 관리자 권한 또는 권한 있는 작업에 대한 액세스를 요청할 수 있습니다. 권한 있는 액세스 기능은 구성된 권한 액세스 정책에 대한 처리 요청을 Microsoft 365로 보내고 보안 준수 센터 로그에 &amp; 활동을 기록합니다.

![2단계: 액세스 요청](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>3단계: 액세스 승인

승인 요청이 생성되어 보류 중인 요청 알림이 승인자에 전자 메일로 전송됩니다. 승인되면 권한이 부여된 액세스 요청이 승인으로 처리되어 작업을 완료할 수 있습니다. 거부된 경우 작업이 차단된 후 요청자에 대한 액세스 권한이 부여되지 않습니다. 요청자에 전자 메일 메시지를 통해 요청 승인 또는 거부에 대한 알림이 제공됩니다.

![3단계: 액세스 승인](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>4단계: 액세스 처리

승인된 요청의 경우 Exchange 관리 실행 영역이 작업을 처리합니다. 권한이 부여된 액세스 정책에 대해 승인을 확인하고 Microsoft 365 기하 도우미에서 처리합니다. 작업에 대한 모든 활동은 보안 준수 센터에 &amp; 기록됩니다.

![4단계: 액세스 처리](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>자주 묻는 질문

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>Office 365에서 권한 있는 액세스를 사용할 수 있는 SKUS는 무엇입니까?

권한 있는 액세스 관리는 다양한 Microsoft 365 및 Office 365 구독 및 추가 기능에서 고객이 사용할 수 있습니다. 자세한 내용은 권한 있는 액세스 [관리 시작을](privileged-access-management-configuration.md) 참조합니다.

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>권한 있는 액세스는 Exchange를 넘어 Office 365 작업을 언제 지원하나요?

권한 있는 액세스 관리는 곧 다른 Office 365 워크로드에서 사용할 수 있습니다. 자세한 내용은 [Microsoft 365 로드맵을](https://www.microsoft.com/microsoft-365/roadmap) 방문합니다.

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>조직에 30개 이상의 권한이 부여된 액세스 정책이 필요합니까? 이 제한을 늘리시겠습니까?

예. 조직당 권한 있는 액세스 정책 30개로 현재 제한을 높이는 것은 기능 로드맵에 있습니다.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>Office 365에서 권한이 부여된 액세스를 관리하려면 전역 관리자로 설정해야 하나요?

아니요. Office 365에서 권한이 부여된 액세스를 관리하는 계정에 Exchange 역할 관리 역할을 할당해야 합니다. 역할 관리 역할을 독립 실행형 계정 권한으로 구성하지 않는 경우 전역 관리자 역할은 기본적으로 이 역할을 포함하며 권한 있는 액세스를 관리할 수 있습니다. 승인자 그룹에 포함된 사용자는 전역 관리자일 필요는 없습니다. 또는 PowerShell을 통해 요청을 검토하고 승인하기 위해 역할 관리 역할을 할당할 필요는 없습니다.

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a>고객 Lockbox와 관련된 권한 있는 액세스 관리는 어떻게 하나요?

[고객 Lockbox는](/office365/admin/manage/customer-lockbox-requests) Microsoft가 데이터에 액세스할 때 조직에 대한 액세스 제어 수준을 허용합니다. 권한이 부여된 액세스 관리를 사용하면 조직 내에서 모든 Microsoft 365 권한 작업을 세밀하게 제어할 수 있습니다.

## <a name="ready-to-get-started"></a>시작할 준비가 되나요?

권한이 부여된 액세스 관리를 위한 조직 [구성을 시작하십시오.](privileged-access-management-configuration.md)

## <a name="learn-more"></a>자세한 정보

[대화형 가이드: 권한이 부여된 액세스 관리를 사용하여 관리자 작업 모니터링 및 제어](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
