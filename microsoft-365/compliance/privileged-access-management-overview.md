---
title: 권한이 부여된 액세스 관리에 대한 자세한 정보
description: 이 문서에서는 FAQ(질문과 대답)Microsoft 365 액세스 관리에 대한 개요를 제공합니다.
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
ms.openlocfilehash: e66f9133959ce7f09915361e7583ae809e33647e
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59221155"
---
# <a name="learn-about-privileged-access-management"></a>권한이 부여된 액세스 관리에 대한 자세한 정보

권한 있는 액세스 관리를 사용하면 Office 365에서 권한 있는 관리자가 실행할 수 있는 작업에 대해 세부적인 액세스 제어를 할 수 있습니다. 중요한 데이터에 대한 액세스 또는 중요한 구성 설정에 대한 액세스가 진행 중인 기존의 권한 있는 관리자 계정을 사용하는 위반로부터 조직을 보호할 수 있습니다. Privileged Access Management는 사용자가 범위가 넓고 시간 제한이 큰 승인 워크플로를 통해 권한 있는 작업을 완료하기 위해 제시간에 액세스 권한을 요청해야 합니다. 이 구성을 통해 사용자는 중요한 데이터나 중요한 구성 설정에 노출될 위험 없이 당면한 작업을 수행할 수 있는 액세스 권한을 얻을 수 있습니다. 조직에서 권한 있는 액세스 관리를 Microsoft 365 권한 없는 권한으로 운영할 수 있으며, 관리 액세스 취약성에 대한 방어 계층을 제공합니다.

통합된 고객 Lockbox 및 권한 있는 액세스 관리 워크플로에 대한 간략한 개요는 이 고객 Lockbox 및 권한 있는 액세스 관리 비디오를 [참조하세요.](https://go.microsoft.com/fwlink/?linkid=2066800)

## <a name="layers-of-protection"></a>보호 계층

권한 있는 액세스 관리 는 Microsoft 365 보안 아키텍처 내의 다른 데이터 및 액세스 기능 보호를 보완합니다. 권한 있는 액세스 관리 를 보안에 대한 통합 및 계층적 접근 방식의 일부로 포함하면 중요한 정보 및 Microsoft 365 구성 설정의 보호를 최대화하는 보안 모델을 제공할 수 있습니다. 다이어그램에 표시된 바와 같이 권한 있는 액세스 관리는 Microsoft 365 데이터의 기본 암호화 및 Microsoft 365 서비스의 역할 기반 액세스 제어 보안 모델과 함께 제공되는 보호를 기반으로 합니다. [Azure AD](/azure/active-directory/active-directory-privileged-identity-management-configure)Privileged Identity Management 사용할 경우 이러한 두 기능은 서로 다른 범위에서 Just-In-Time 액세스를 통해 액세스 제어를 제공합니다.

![계층적 보호를 Microsoft 365.](../media/pam-layered-protection.png)

권한 있는 액세스 관리는 작업  수준에서 정의되고 범위가 지정되는 반면 Azure  AD Privileged Identity Management 여러 작업을 실행할 수 있는 기능으로 역할 수준에서 보호를 적용합니다. Azure AD Privileged Identity Management는 주로 AD 역할 및 역할 그룹에 대한 액세스를 관리할 수 있으며, Microsoft 365의 권한 있는 액세스 관리는 작업 수준에서만 적용됩니다.

- **Azure AD 계정을** 이미 사용하는 동안 권한 있는 액세스 관리를 Privileged Identity Management. 권한 있는 액세스 관리를 추가하면 사용자 데이터에 대한 권한 있는 액세스에 대한 또 다른 세부적인 보호 및 감사 Microsoft 365 있습니다.

- **Azure AD Privileged Identity Management 권한** 있는 액세스 관리를 이미 사용하고 있는 동안 다음 Office 365.  Azure AD Privileged Identity Management 권한 있는 액세스 관리에 추가하면 사용자 역할 또는 ID에 의해 Microsoft 365 외부의 데이터에 대한 권한 있는 액세스를 확장할 수 있습니다.  

## <a name="privileged-access-management-architecture-and-process-flow"></a>권한이 부여된 액세스 관리 아키텍처 및 프로세스 흐름

다음의 각 프로세스 흐름은 권한 있는 액세스의 아키텍처와 권한 있는 액세스가 Microsoft 365, 감사 및 Exchange 실행 영역과 상호 작용하는 방식을 간략하게 설명합니다.

### <a name="step-1-configure-a-privileged-access-policy"></a>1단계: 권한 있는 액세스 정책 구성하기

Microsoft 365 관리 센터 또는 Exchange 관리 PowerShell을 사용하여 권한 있는 액세스 정책을 구성하는 경우 정책 및 권한 있는 액세스 기능 프로세스 및 정책 특성을 Microsoft 365 구성합니다. [](https://admin.microsoft.com) 활동은 보안 및 준수 &amp; 센터에 기록됩니다. 이 정책은 이제 사용하도록 설정되었으며 승인을 위해 들어오는 요청을 처리할 준비가 완료되었습니다.

![1단계: 정책 만들기.](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>2단계: 액세스 요청

사용자 [Microsoft 365 관리 센터](https://admin.microsoft.com) 또는 Exchange PowerShell을 사용하여 상승되거나 권한이 부여된 작업에 대한 액세스를 요청할 수 있습니다. 권한 있는 액세스 기능은 구성된 권한 액세스 정책에 대해 처리하기 위해 Microsoft 365 요청을 전송하고 보안 및 준수 센터 로그에 &amp; 활동을 기록합니다.

![2단계: 액세스 요청.](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>3단계: 액세스 승인

승인 요청이 생성되며, 보류 중인 요청 알림이 승인자에게 전자 메일로 전송됩니다. 승인될 경우, 권한 있는 액세스 요청은 승인으로 처리되며, 해당 작업은 완료할 준비가 됩니다. 승인 거부될 경우, 해당 작업은 차단되며, 요청자에 대한 액세스 권한이 부여되지 않습니다. 요청자는 전자 메일 메시지를 통해 요청 승인 또는 거부 관련 알림을 받습니다.

![3단계: 액세스 승인.](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>4단계: 액세스 처리

승인된 요청의 경우, 해당 작업은 Exchange 관리의 Runspace에서 실행됩니다. 승인은 권한 있는 액세스 정책에 대해 점검되며, Microsoft 365에서 처리됩니다. 작업에 대한 모든 활동은 보안 및 준수 &amp; 센터에 기록됩니다.

![4단계: 액세스 처리.](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>질문과 대답

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>어떤 SKUS에서 권한 있는 액세스를 사용할 수 Office 365?

권한 있는 액세스 관리는 다양한 구독 및 Microsoft 365 추가 Office 365 사용할 수 있습니다. 자세한 [내용은 권한 있는](privileged-access-management-configuration.md) 액세스 관리 시작을 참조합니다.

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>권한이 부여된 액세스는 Office 365 이상으로 지원되는 Exchange?

권한 있는 액세스 관리는 다른 모든 작업 Office 365 사용할 수 있습니다. 자세한 [Microsoft 365 로드맵을](https://www.microsoft.com/microsoft-365/roadmap) 방문합니다.

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>조직에 30개 이상의 권한 있는 액세스 정책이 필요합니까? 이 제한을 늘리나요?

예. 조직당 권한 있는 액세스 정책 30개로 현재 제한을 올리는 것은 기능 로드맵에 있습니다.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>사용자 계정에서 권한이 부여된 액세스를 관리하려면 전역 Office 365?

아니요. 역할 Exchange 권한을 관리하는 계정에 역할 관리 역할이 할당되어 Office 365. 역할 관리 역할을 독립 실행형 계정 권한으로 구성하지 않는 경우 전역 관리자 역할은 기본적으로 이 역할을 포함하며 권한 있는 액세스를 관리할 수 있습니다. 승인자 그룹에 포함된 사용자는 PowerShell을 통해 요청을 검토하고 승인하기 위해 전역 관리자 또는 역할 관리 역할을 할당할 필요가 없습니다.

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a>고객 Lockbox와 관련된 권한 있는 액세스 관리는 어떻게 하나요?

[Customer Lockbox는](/office365/admin/manage/customer-lockbox-requests) Microsoft에서 데이터에 액세스할 때 조직에 대한 액세스 제어 수준을 허용합니다. 권한이 부여된 액세스 관리를 사용하면 조직 내의 모든 권한 있는 작업에서 세밀한 액세스 Microsoft 365 수 있습니다.

## <a name="ready-to-get-started"></a>시작할 준비가 되셨나요?

권한이 [부여된 액세스 관리에 대한 조직 구성을 시작하십시오.](privileged-access-management-configuration.md)

## <a name="learn-more"></a>자세히 알아보기

[대화형 가이드: 권한 있는 액세스 관리를 사용하여 관리자 작업 모니터링 및 제어](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
